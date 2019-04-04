def main():

  import sys
  #libraries:
  game = [[' ', 'A ', 'B ', 'C '], ['1', '_', '|', '_', '|', '_'], ['2', '_', '|', '_', '|', '_'], ['3', ' ', '|', ' ', '|', ' ']]
  dictionary = {'1': 1, '2': 2, '3': 3, 'a': 1, 'b': 3, 'c': 5}
  user_past_moves = []
  comp_past_moves = []

  #print emptyfield and instructions
  for row in game:
    print(''.join(row))
  print('When selecting the field you wish to mark, write the letter first and then the number.')

  #set variables
  X_or_O_correctly_chosen = False
  user_symbol = ''
  computer_symbol = ''

  #player chooses X or O
  while not X_or_O_correctly_chosen:
    user_symbol = input('Choose which mark you would like to use, X or O: ').lower()
    if 'x' in user_symbol:
      user_symbol = 'x'
      computer_symbol = 'o'
      X_or_O_correctly_chosen = True
    elif 'o' in user_symbol:
      user_symbol = 'o'
      computer_symbol = 'x'
      X_or_O_correctly_chosen = True
    else:
      print('Oops. Wrong input. Try again.')

  #Computer's turn
  def compmove(letter, number):
    game[number][letter] = computer_symbol 
    return
  
  def printgame(): #defining printing the field.
    for row in game:
      print(''.join(row))

  def play_again():
    new_game = input('Would you like to try again? Please enter yes or no: ').lower()
    if new_game == 'yes':
      main()
    else:
      print('Thanks for playing!')
      sys.exit()

  compmove(1, 3) #first move
  comp_past_moves.append('a3')

  printgame()

  user_move = True
  acceptable_values = ['a1', 'a2', 'a3', 'b1', 'b2', 'b3', 'c1', 'c2', 'c3'] #values accepted as input.
  moves = []

  #the game:
  while user_move:
    user_move = input('Select a field to mark with ' + user_symbol + ': ').lower()
    if user_move in acceptable_values and user_move not in user_past_moves and user_move not in comp_past_moves:
      #user's move
      user_past_moves.append(user_move)
      letter = user_move[0]
      number = user_move[1]
      game[1][4]
      game[dictionary[number]][dictionary[letter]] = user_symbol
    
      #computer's move:
      #1 b2_______________________________________
      if len(user_past_moves) == 1 and 'b2' == user_past_moves[0] and 'a3' in comp_past_moves:
        compmove(5, 1)
        comp_past_moves.append('c1')
      
      #2 b2 a1
      if len(user_past_moves) == 2 and ['b2', 'a1'] == user_past_moves and 'c1' in comp_past_moves:
        compmove(5, 3)
        comp_past_moves.append('c3')
      #3 b2 a1 - end game
      if len(user_past_moves) == 3 and ['b2','a1'] == user_past_moves[:2] and ['a3', 'c1', 'c3'] == comp_past_moves:
        if 'b3' in user_past_moves:
          compmove(5, 2)
        else:
          compmove(3, 3)
        printgame()      
        print('You loose!')
        play_again()
      
      #2 b2 c3
      if len(user_past_moves) == 2 and ['b2', 'c3'] == user_past_moves and 'c1' in comp_past_moves:
        compmove(1, 1)
        comp_past_moves.append('a1')  
      #3 b2 c3 - end game
      if len(user_past_moves) == 3 and ['b2','c3'] == user_past_moves[:2] and ['a3', 'c1', 'a1'] == comp_past_moves:
        if 'a2' in user_past_moves:
          compmove(3, 1)
          printgame()
          print('You loose!')
          play_again()
        else:
          compmove(1, 2)
          printgame()
          print('You loose!')
          play_again()

      #blocking until draw:
      #2 b2 b1
      if len(user_past_moves) == 2 and ['b2', 'b1'] == user_past_moves and 'c1' in comp_past_moves:
        compmove(3, 3)
        comp_past_moves.append('b3')
      #3 b2 b1 - one end game
      if len(user_past_moves) == 3 and ['b2','b1'] == user_past_moves[:2] and ['a3', 'c1', 'b3'] == comp_past_moves:
        if 'c3' in user_past_moves:
          compmove(1,1)
          comp_past_moves.append('a1')
        else:
          compmove(5, 3)
          printgame()
          print('You loose!')
          play_again()      
      #4 b2 b1 c3 - end game
      if len(user_past_moves) == 4 and ['b2','b1','c3'] == user_past_moves[:3] and ['a3', 'c1', 'b3', 'a1'] == comp_past_moves:
        if 'a2' in user_past_moves:
          compmove(5,2)
          printgame()
          print("It's a draw!")
          play_again()
        else:
          compmove(5, 3)
          printgame()
          print('You loose!')
          play_again()
      
      #2 b2 a2
      if len(user_past_moves) == 2 and ['b2', 'a2'] == user_past_moves and 'c1' in comp_past_moves:
        compmove(5, 2)
        comp_past_moves.append('c2')
      #3 b2 a2 - one end game
      if len(user_past_moves) == 3 and ['b2','a2'] == user_past_moves[:2] and ['a3', 'c1', 'c2'] == comp_past_moves:
        if 'c3' in user_past_moves:
          compmove(1,1)
          comp_past_moves.append('a1')
        else:
          compmove(5, 3)
          printgame()
          print('You loose!')
          play_again()      
      #4 b2 a2 c3 - end game
      if len(user_past_moves) == 4 and ['b2','a2','c3'] == user_past_moves[:3] and ['a3', 'c1', 'c2', 'a1'] == comp_past_moves:
        if 'b1' in user_past_moves:
          compmove(3,3)
          printgame()
          print("It's a draw!")
          play_again()
        else:
          compmove(3, 1)
          printgame()
          print('You loose!')
          play_again()

      #2 b2 c2
      if len(user_past_moves) == 2 and ['b2', 'c2'] == user_past_moves and 'c1' in comp_past_moves:
        compmove(1, 2)
        comp_past_moves.append('a2')
      #3 b2 c2 - one end game
      if len(user_past_moves) == 3 and ['b2','c2'] == user_past_moves[:2] and ['a3', 'c1', 'a2'] == comp_past_moves:
        if 'a1' in user_past_moves:
          compmove(5,3)
          comp_past_moves.append('c3')
        else:
          compmove(1, 1)
          printgame()
          print('You loose!')
          play_again()      
      #4 b2 c2 a1 - end game
      if len(user_past_moves) == 4 and ['b2','c2','a1'] == user_past_moves[:3] and ['a3', 'c1', 'a2', 'c3'] == comp_past_moves:
        if 'b3' in user_past_moves:
          compmove(3,1)
          printgame()
          print("It's a draw!")
          play_again()
        else:
          compmove(3, 3)
          printgame()
          print('You loose!')
          play_again()

      #2 b2 b3
      if len(user_past_moves) == 2 and ['b2', 'b3'] == user_past_moves and 'c1' in comp_past_moves:
        compmove(3, 1)
        comp_past_moves.append('b1')
      #3 b2 b3 - one end game
      if len(user_past_moves) == 3 and ['b2','b3'] == user_past_moves[:2] and ['a3', 'c1', 'b1'] == comp_past_moves:
        if 'a1' in user_past_moves:
          compmove(5,3)
          comp_past_moves.append('c3')
        else:
          compmove(1, 1)
          printgame()
          print('You loose!')
          play_again()      
      #4 b2 b3 a1 - end game
      if len(user_past_moves) == 4 and ['b2','b3','a1'] == user_past_moves[:3] and ['a3', 'c1', 'b1', 'c3'] == comp_past_moves:
        if 'c2' in user_past_moves:
          compmove(1,2)
          printgame()
          print("It's a draw!")
          play_again()
        else:
          compmove(5, 2)
          printgame()
          print('You loose!')
          play_again()
      
      #1 a1_______________________________________
      if len(user_past_moves) == 1 and 'a1' == user_past_moves[0] and 'a3' in comp_past_moves:
        compmove(5, 3)
        comp_past_moves.append('c3')
      
      #2 a1 b3
      elif len(user_past_moves) == 2 and ['a1', 'b3'] == user_past_moves and 'c3' in comp_past_moves:
        compmove(5, 1)
        comp_past_moves.append('c1')
      #3 a1 b3 - end game
      elif len(user_past_moves) == 3 and ['a1','b3'] == user_past_moves[:2] and ['a3', 'c3', 'c1'] == comp_past_moves:
        if 'b2' in user_past_moves:
          compmove(5, 2)
          printgame()
          print('You loose!')
          play_again()
        else:
          compmove(3, 2)
          printgame()
          print('You loose!')
          play_again()
      #2 a1 - end game
      elif len(user_past_moves) == 2 and 'a1' == user_past_moves[0]:
        compmove(3, 3)
        printgame()      
        print('You loose!')
        play_again()

      #1 b1_______________________________________
      if len(user_past_moves) == 1 and 'b1' == user_past_moves[0] and 'a3' in comp_past_moves:
        compmove(5, 3)
        comp_past_moves.append('c3')
      
      #2 b1 b3
      elif len(user_past_moves) == 2 and ['b1', 'b3'] == user_past_moves and 'c3' in comp_past_moves:
        compmove(3, 2)
        comp_past_moves.append('b2')
      #3 b1 b3 - end game
      elif len(user_past_moves) == 3 and ['b1','b3'] == user_past_moves[:2] and ['a3', 'c3', 'b2'] == comp_past_moves:
        if 'c1' in user_past_moves:
          compmove(1, 1)
          comp_past_moves.append('a1')
        else:
          compmove(5, 1)
          printgame()
          print('You loose!')
          play_again()
      #4 b1 b3 c1 - end game
      elif len(user_past_moves) == 4 and ['b1','b3','c1'] == user_past_moves[:3] and ['a3', 'c3', 'b2', 'a1'] == comp_past_moves:
        if 'a2' in user_past_moves:
          compmove(5,2)
          printgame()
          print("It's a draw!")
          play_again()
        else:
          compmove(1, 2)
          printgame()
          print('You loose!')
          play_again()
      #2 b1 - end game
      elif len(user_past_moves) == 2 and 'b1' == user_past_moves[0]:
        compmove(3, 3)
        printgame()      
        print('You loose!')
        play_again()

      #1 c1_______________________________________
      if len(user_past_moves) == 1 and 'c1' == user_past_moves[0] and 'a3' in comp_past_moves:
        compmove(1, 1)
        comp_past_moves.append('a1')
      
      #2 c1 a2
      elif len(user_past_moves) == 2 and ['c1', 'a2'] == user_past_moves and 'a1' in comp_past_moves:
        compmove(5, 3)
        comp_past_moves.append('c3')
      #3 c1 a2 - end game
      elif len(user_past_moves) == 3 and ['c1','a2'] == user_past_moves[:2] and ['a3', 'a1', 'c3'] == comp_past_moves:
        if 'b2' in user_past_moves:
          compmove(3, 3)
          printgame()
          print('You loose!')
          play_again()
        else:
          compmove(3, 2)
          printgame()
          print('You loose!')
          play_again()
      #2 c1 - end game
      elif len(user_past_moves) == 2 and 'c1' == user_past_moves[0]:
        compmove(1, 2)
        printgame()      
        print('You loose!')
        play_again()

      #1 a2_______________________________________
      if len(user_past_moves) == 1 and 'a2' == user_past_moves[0] and 'a3' in comp_past_moves:
        compmove(5, 3)
        comp_past_moves.append('c3')
      
      #2 a2 b3
      elif len(user_past_moves) == 2 and ['a2', 'b3'] == user_past_moves and 'c3' in comp_past_moves:
        compmove(5, 1)
        comp_past_moves.append('c1')
      #3 a2 b3 - end game
      elif len(user_past_moves) == 3 and ['a2','b3'] == user_past_moves[:2] and ['a3', 'c3', 'c1'] == comp_past_moves:
        if 'b2' in user_past_moves:
          compmove(5, 2)
          printgame()
          print('You loose!')
          play_again()
        else:
          compmove(3, 2)
          printgame()
          print('You loose!')
          play_again()
      #2 a2 - end game
      elif len(user_past_moves) == 2 and 'a2' == user_past_moves[0]:
        compmove(3, 3)
        printgame()      
        print('You loose!')
        play_again()

      #1 c2_______________________________________
      if len(user_past_moves) == 1 and 'c2' == user_past_moves[0] and 'a3' in comp_past_moves:
        compmove(1, 1)
        comp_past_moves.append('a1')
      
      #2 c2 a2
      elif len(user_past_moves) == 2 and ['c2', 'a2'] == user_past_moves and 'a1' in comp_past_moves:
        compmove(3, 2)
        comp_past_moves.append('b2')
      #3 c2 a2 - end game
      elif len(user_past_moves) == 3 and ['c2','a2'] == user_past_moves[:2] and ['a3', 'a1', 'b2'] == comp_past_moves:
        if 'c1' in user_past_moves:
          compmove(5, 3)
          printgame()
          print('You loose!')
          play_again()
        else:
          compmove(5, 1)
          printgame()
          print('You loose!')
          play_again()
      #2 c2 - end game
      elif len(user_past_moves) == 2 and 'c2' == user_past_moves[0]:
        compmove(1, 2)
        printgame()      
        print('You loose!')
        play_again()    

      #1 b3_______________________________________
      if len(user_past_moves) == 1 and 'b3' == user_past_moves[0] and 'a3' in comp_past_moves:
        compmove(1, 1)
        comp_past_moves.append('a1')
      
      #2 b3 a2
      elif len(user_past_moves) == 2 and ['b3', 'a2'] == user_past_moves and 'a1' in comp_past_moves:
        compmove(5, 1)
        comp_past_moves.append('c1')
      #3 b3 a2 - end game
      elif len(user_past_moves) == 3 and ['b3','a2'] == user_past_moves[:2] and ['a3', 'a1', 'c1'] == comp_past_moves:
        if 'b1' in user_past_moves:
          compmove(3, 2)
          printgame()
          print('You loose!')
          play_again()
        else:
          compmove(3, 1)
          printgame()
          print('You loose!')
          play_again()
      #2 b3 - end game
      elif len(user_past_moves) == 2 and 'b3' == user_past_moves[0]:
        compmove(1, 2)
        printgame()      
        print('You loose!')
        play_again()

      #1 c3_______________________________________
      if len(user_past_moves) == 1 and 'c3' == user_past_moves[0] and 'a3' in comp_past_moves:
        compmove(1, 1)
        comp_past_moves.append('a1')
      
      #2 c3 a2
      elif len(user_past_moves) == 2 and ['c3', 'a2'] == user_past_moves and 'a1' in comp_past_moves:
        compmove(5, 1)
        comp_past_moves.append('c1')
      #3 c3 a2 - end game
      elif len(user_past_moves) == 3 and ['c3','a2'] == user_past_moves[:2] and ['a3', 'a1', 'c1'] == comp_past_moves:
        if 'b1' in user_past_moves:
          compmove(3, 2)
          printgame()
          print('You loose!')
          play_again()
        else:
          compmove(3, 1)
          printgame()
          print('You loose!')
          play_again()
      #2 c3 - end game
      elif len(user_past_moves) == 2 and 'c3' == user_past_moves[0]:
        compmove(1, 2)
        printgame()      
        print('You loose!')
        play_again()

      printgame()

    #if input is incorrect
    elif not user_move: #if field is empty
      print('Thanks for playing!')
    elif user_move in user_past_moves:
      print('Sorry, that field is already marked.Please select another one.')
    else: #if the move is not within parameters
      print('Oops! Wrong value. Please make sure you write the letter first and then the number and that there is no space between.')

main()
