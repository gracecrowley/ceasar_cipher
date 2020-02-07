def decrypt(message,offset):
  mess_decrypt =""
  for letter in range(0,len(message)):
    
      unicodes = ord(message[letter])
      
      if unicodes == 32:
        with_offset = 32
      
      else:
       with_offset = unicodes - offset
      
      if with_offset == 32:
        with_offset = 32
      elif with_offset <= 64:
        with_offset = with_offset + 26
       
      
      rev_unicode = chr(with_offset)
      mess_decrypt = mess_decrypt + rev_unicode
    
  return(mess_decrypt)


loop = True
while loop ==True:
  message = input("Please enter message to be decrypted (press enter to end)\n")
  
  if message =="":
    loop = False
  else:
    user_offset =int(input("Please enter an offset\n"))
    offset = user_offset % 26
    print(decrypt(message,offset))
