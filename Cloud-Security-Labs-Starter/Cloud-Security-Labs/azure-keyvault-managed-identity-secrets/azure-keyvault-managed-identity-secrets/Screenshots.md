1. Associate the managed identity with the VM
   ![Image](https://github.com/user-attachments/assets/0451d8f9-7d24-40bd-ae27-6bb2f7669a53)

2. Create a new Key Vault:
   ![Image](https://github.com/user-attachments/assets/992dc3f5-c955-4e19-b293-182cf63a8007)

3. Create Private Endpoint in the Key Vault
   ![Image](https://github.com/user-attachments/assets/367af850-138b-4952-a42a-8da9094c3f39)

   ![Image](https://github.com/user-attachments/assets/1c186f4d-8de5-4580-a443-94d7915bd347)

 4. Use PowerShell to create and read secrets in Key Vault
    a. Log in to Azure using managed identity:
    ![Image](https://github.com/user-attachments/assets/75822937-8142-4dfc-98ab-f38498a4c644)

    b. Capture a secure string to store:
    ![Image](https://github.com/user-attachments/assets/7b8c8c19-b965-42d1-bec4-06e2513041cd)

    c. Get the Key Vault and save it to a variable called kv, then Check the key is returned:
    ![Image](https://github.com/user-attachments/assets/79a892a0-57b6-4799-8326-4741ee40d759)

    d. Create a Key Vault secret:
    ![Image](https://github.com/user-attachments/assets/f30fad10-3e0e-4cca-b515-cfd6ef36b9b5)

    e. Retrieve a secret from Key Vault (as plain text):
    ![Image](https://github.com/user-attachments/assets/6c51a1dc-c1af-4b01-88b7-0a6cdc3ee28c)
