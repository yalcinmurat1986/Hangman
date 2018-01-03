
# Hangman


import random
def hangman(a):
    mistake = 0
    a= a.split()
    word = random.choice(a)
    print('word consist of',len(word),'letters')
    print('If you make 3 mistakes you lose')
    guess = [0]*len(word)
    #print(word)
    #print(guess)
    word_list = [i for i in word]
    while (guess != word_list):
        letter = input('Please enter your letter')

        for index,i in enumerate(word):
            #print('i:',i)
            if letter == i:
                print('You found letter', (index+1))
                guess[index] = letter
                #print(guess)
                #print(word)
        if letter not in word:
            mistake += 1
            print('number of mistakes', mistake,'/3')
            
            if mistake == 3:
                print('game over')
                break
            print('try again')
    if guess == word_list:
        print('you win') 
    return
    
   
a =('There is no substitute for hard work')
hangman(a)
