# Lab-Exercise---5---Rail-fence

## AIM :
To implement the Rail Fence Cipher algorithm for encrypting plaintext using Python.

## Procedure :

1. Start the program and enter the plaintext to be encrypted.
2. Enter the number of rails to be used for encryption.
3. Arrange the plaintext characters in a zigzag pattern across the specified number of rails.
4. Read the characters row by row to generate the encrypted text.
5. Display the encrypted message.
6. Test the algorithm with different plaintexts and rail values to verify the results.

## Program :
```
def rail_fence_encrypt(text, rails):
    fence = [['\n' for _ in range(len(text))]
             for _ in range(rails)]

    row = 0
    direction = 1

    for col, char in enumerate(text):
        fence[row][col] = char

        if row == 0:
            direction = 1
        elif row == rails - 1:
            direction = -1

        row += direction

    encrypted_text = ""

    for row in fence:
        for char in row:
            if char != '\n':
                encrypted_text += char

    return encrypted_text


message = input("Enter the plaintext: ")
rails = int(input("Enter the number of rails: "))

ciphertext = rail_fence_encrypt(message, rails)

print("Plaintext:", message)
print("Encrypted text:", ciphertext)
```
## Output :
<img width="1275" height="1020" alt="image" src="https://github.com/user-attachments/assets/a976e264-51e9-4bf7-b55d-1d416e829f13" />

## Result :
Thus, the program is executed successfully.
