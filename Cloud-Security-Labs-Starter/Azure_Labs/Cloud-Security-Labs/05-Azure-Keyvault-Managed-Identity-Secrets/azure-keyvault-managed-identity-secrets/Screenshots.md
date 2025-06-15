**1. Associate the managed identity with the VM**

   ![Image](https://github.com/user-attachments/assets/0451d8f9-7d24-40bd-ae27-6bb2f7669a53)


**2. Create a new Key Vault:**

   ![Image](https://github.com/user-attachments/assets/992dc3f5-c955-4e19-b293-182cf63a8007)


**3. Create Private Endpoint in the Key Vault**

   ![Image](https://github.com/user-attachments/assets/367af850-138b-4952-a42a-8da9094c3f39)


   ![Image](https://github.com/user-attachments/assets/1c186f4d-8de5-4580-a443-94d7915bd347)


 **4. Use PowerShell to create and read secrets in Key Vault:**
    
    - Log in to Azure using managed identity:

   ![Image](https://github.com/user-attachments/assets/de3cfc57-2401-49c5-adfa-f8a4efc98707)

    - Capture a secure string to store:

   ![Image](https://github.com/user-attachments/assets/e9854c56-5df2-4908-8233-7b9b8c980b40)

    - Get the Key Vault and save it to a variable called kv, then Check the key is returned:
    
   ![Image](https://github.com/user-attachments/assets/a07c200e-ee29-4c69-a892-5d2f283af47c)

    - Create a Key Vault secret:

   ![Image](https://github.com/user-attachments/assets/c61c8230-ed45-4d08-ae43-68f14e504599)

    - Retrieve a secret from Key Vault (as plain text):

   ![Image](https://github.com/user-attachments/assets/6c51a1dc-c1af-4b01-88b7-0a6cdc3ee28c)
