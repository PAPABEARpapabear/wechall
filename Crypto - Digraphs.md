```
#!/usr/bin/python
import re

cipher = "zuuhymqisobuvcuwbabuvcieuhymmiqx xfuhuw ergstesocfkfvcgser vcwbiemi pxgsmimibuqigs miuwtetegsmimiptuwbabacfqx sabumi ymuhvc vcuhuh erieptptieteuwbavc gsievcwbgssozf atbumi ievcde sagsbabazf qiuhuher bhuhjdqx zsymvcgsso vcwbiemi azgscfatuhsoer bumi miuhbauwvcieuhymyl teerymmierpxkftesogsiebuqx"

two_to_one_table = {
    "qx": ".",
    "zu": "C",
    "uh": "O",
    "ym": "N",
    "qi": "G",
    "so": "R",
    "bu": "A",
    "vc": "T",
    "uw": "U",
    "ba": "L",
    "ie": "I",
    "mi": "S",
    "xf": "Y",
    "wb": "H",
    "er": "D",
    "gs": "E",
    "te": "C",
    "cf": "Y",
    "kf": "P",
    "px": "M",
    "pt": "F",
    "zf": ",",
    "zs": "E",
    "az": "K",
    "at": "W",
    "de": "?",
    "sa": "W"
}

def replace_sentence():
    plain_parts = []
    for each_cipher_word in cipher.split(" "):
        plain_parts.append(replace_one_word(each_cipher_word))

    return " ".join(plain_parts)

def replace_one_word(one_word):
    cipher_parts = re.findall(r'.{2}', one_word)
    plain_parts = cipher_parts
    for each_key, each_value in two_to_one_table.items():
        for cipher_part_index in range(0, len(cipher_parts)):
            if each_key == cipher_parts[cipher_part_index]:
                plain_parts[cipher_part_index] = each_value

    return "".join(plain_parts)

def main():
    print(replace_sentence())

if __name__ == "__main__":
    main()

```
Plain text(not decrypt all character pair to get the solution):  
CONGRATULATIONS. YOU DECRYPTED THIS MESSAGE SUCCESSFULLY. WAS NOT TOO DIFFICULT EITHER, WAS IT? WELL, GOOD bhOjd. ENTER THIS KEYWORD AS SOLUTIONyl CDNSDMPCREIA.
