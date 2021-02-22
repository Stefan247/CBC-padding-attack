Tema IC 2020
Nemtuc Ilie-Stefan, 343C4

CBC Padding Attack

Functii utile:
-> Blockify: Imparte bytestream-ul 'text' intr-o lista de 'bytestrings' de dimensiune maxima `block_size`
-> Validate_padding: Returneaza true daca bytestream-ul este padded corect, altfel false (0x01, 0x02 0x02, 0x03 0x03 0x03 etc.)
-> pkcs7_pad: Completeaza cu padding
-> pkcs7_depad: Daca padding este valid, atunci se returneaza bytestream-ul fara padding, altfel None

CBC-padding-attack algorithm (short):

r - random bytes
`
for-each block:
	->initial 0 padding 
	->empty list
	
	for j = 0, 16 (block index r/IV)
		cs = first part of r || i (0 - 256) || padding-to-blocksize -> plaintext xor padding bits
		for a certain i, the oracle will return true -> correct bit from the plaintext.

return final message`
