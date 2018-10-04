# Classical ciphers

They were all symmetric.

## Introduction

Cyptography used to be used by the powerful and the military.
With the rise of computers it's necessary for everyone to use cypto.

## Early ciphers

- symmetric
- subtitution or transposition
- pen & paper

- easy to break
- easy to ake mistakes

- Transposition
  Ex: Rail Fence
  Permutates the plaintext.
  Classicly done with some device (Ex: skytale)

  Rail Fence:
  THISISATEST
	|
	v
  T...I...E..
  .H.S.S.T.S.
  ..I...A...T
	|
	v
  TIEHSSTSIAT

  Could be improved:
  - Double encryption
  - combine with cipher

- Subsitution
  Ex: Ceaser
  Individual letters are replaced by other symbols.
  The order isn't changed.

  Multiple types:
  - monoalphabetic: 1 to 1
    Generalised ceaser: shift by a constant.
    Weaknesses:
    - Frquency analysis
    - Cribs
    - Underlying word or pattern
    
  - Homophonic: letters to more than one possibillity
    Ex: map each letter to a couple of numbers in 0-99
    Combats frequency analysis (choose more mappings for common letters such as 'e')

    Famous exampls:
    Beale ciphers

  - Polyalphabetic: mutiple alphabets at once (many-to-many)
    Ex: shift be a sequence of numbers. One single number would be generalised ceaser.

    Viginaire cipher (falsly attributed to Blaise de Vigenère)
    Initially thought to be unbreakable.
    Each cipher letter is derived by combining each key letter with the corresponding plaintext letter/
      - repeat until all plaintext is encrypted
    Selecting the key:
	- Cyclic key
	- Book
	- AutoKey
    
  - polygraphc: substitute groups.
   Ex: playfair
   Uses 5x5 square based on a keyword. Encrypt 2 letters at a time.



  
- polygraphic
  

- playfair