hra_bezi = True

#def pl_vlajka(radky,sloupce):# definovane funkce , napsano na zkousku nez byla napsana CZ vlajka 
#  for radek in range(radky):
#    for sloupec in range(sloupce):
#      if radek < radky // 2:
#        print("*", end = " ")
#      else:
#        print("-", end = " ")
#    print()

def cz_vlajka(radky,sloupce):
  for radek in range(1,radky //2):
    for sloupec in range(radek):
      print("\u2591", end = " ")
    for sloupec in range(sloupce - radek):
      print("\u2588", end = " ")
    print()
  for radek in reversed (range(1,radky //2)):
    for sloupec in range(radek):
      print("\u2591", end = " ")
    for sloupec in range(sloupce - radek):
      print("\u2592", end = " ")
    print()



def de_vlajka(radky,sloupce):
  for radek in range(radky):
    for sloupec in range(sloupce):
      if radek < radky // 3:
        print("\u2588", end = " ")
      elif radek >= (radky // 3) and radek <(radky // 3) * 2 :
        print("\u2592", end = " ")
      else:
        print("\u2591", end = " ")
    print()


def us_vlajka(radky,sloupce):
  for radek in range(radky):
    for sloupec in range(sloupce):
      if sloupec < sloupce // 2 and radek < radky //2:
        print("*", end = " ")
      else: 
        print("\u2591", end = " ")
    print()


while hra_bezi:

  print(">>>>VLAJKY<<<<")
  print("1-CZ")
  print("2-DE")
  print("3-US")
  


  try: # blok try / except osetri chybu pri zadani pismena misto cisla


    otazka = int(input("Zadej cislo vlajky: "))

  except ValueError:

    print("Nezvolil jsi cislo, zvol cislo v rozpeti 1-3!")  

  else:   


    if otazka == 1:

      cz_vlajka(12,20)
      

    elif otazka == 2:

      de_vlajka(12,20)

    elif otazka == 3:
      
      us_vlajka(12,20)
           
    else: 
      print("Nezvolil jsi spravne cislo, vyber cislo v rozpeti 1-3 a vyber vlajku!")
      continue

    odpoved = input("Chces hrat dal ? a/n")
    if odpoved.upper() != "A":
      hra_bezi = False
print("Konec hry")


