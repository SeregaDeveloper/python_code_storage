from hashlib import sha256
from itertools import *
chars = "abcdefghijklnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890"

"""
For tests
count = 4
hash = "a75067a712a160acf1f58a6e617aaf78d7e7ddc8e7d0932c0a9071c4d1f60c07"
end_word = "zClBeUPK4AVb7TFr"
"""
def Change(sym):

   new_chars = input("Enter in line all new characters. Example: abcdefg etc.\n")
   sym += new_chars
   return sym
def Recover():
   length = input("How many unknown symbols ? \n")
   length = int(length)
   end_word = input("Enter well-known part of password\n")
   hash = input("Enter the hashsum\n")
   place = input("Where is the well-known part: 1 - before, 2 - after\n")
   for i in product(chars, repeat = length):
      word =""
      b = ""
      for j in range (0,length):
         b+=i[j]
      if (place == 2):
         word +=b
         word +=end_word
      else:
         word +=end_word
         word +=b
      word = word.encode('UTF-8')
      hashsum = sha256(word).hexdigest()
      if (hash == hashsum):
         print(word)
         print(hashsum)
         break
   return 0
if __name__ == "__main__":
   print ("Programm for password recovery \n"
          "Author: https://github.com/SeregaDeveloper\n"
          "Repository:\n"
          "Current alphabet:", chars)
   change = input("Want to change alphabet? y/n")
   if (change == 'n'):
      Recover()
   if (change == 'y'):
      chars = Change(chars)
      print("Current alphabet:", chars)
      Recover()
