1. Create a Storage Account

![Image](https://github.com/user-attachments/assets/43b28c03-4f80-4284-8455-c681d28fca1f)

2. Use RDP to Connect to the Virtual Machine

![Image](https://github.com/user-attachments/assets/1427a0cc-2e5f-43d8-8408-7180314012e0)

3. Open Azure Storage Explorer and connect to the Azure account

![Image](https://github.com/user-attachments/assets/9291095d-a6ad-4d5f-81cd-989c92714a5d)

4. Upload images

![Image](https://github.com/user-attachments/assets/8888bc9f-3798-4077-a447-fed2263185af)

5. Connect to Storage Account

![Image](https://github.com/user-attachments/assets/7e36c091-a7ef-4103-88f5-1a324026dcb9)

- Files uploaded successfully

![Image](https://github.com/user-attachments/assets/7a0ff864-27cf-4d28-8a2d-a4e2df92f26c)

- Files downloaded successfully

![Image](https://github.com/user-attachments/assets/8717b8a8-4009-4075-872d-369b66744f05)

6. Revoke access to Storage account by regenerating access key

![Image](https://github.com/user-attachments/assets/c8590e06-a240-4118-974d-dd9f8857d09f)

- Access to storage account is now denied

![Image](https://github.com/user-attachments/assets/dd265fe5-2841-4d01-9d6e-499253077963)

- Part 2: Provide More Granular Permissions Using a Shared Access Signature

1. Configure the SAS permissions

![Image](https://github.com/user-attachments/assets/faea8b84-5e05-444f-8590-e8c55267244b)

2. Connect with new SAS

![Image](https://github.com/user-attachments/assets/516465f5-d393-4c43-97e6-df71f295976f)

- Error received because access was not allowed to the container or objects contained within

![Image](https://github.com/user-attachments/assets/7a194e50-cf7d-4b08-b142-73950af4ee73)

3. Create new SAS with allowed container and object access

![Image](https://github.com/user-attachments/assets/7375e510-3bee-46e7-ac39-aacad8116b6c)

![Image](https://github.com/user-attachments/assets/343c05ec-a13a-4af5-9f32-5d4b8ee6d542)

- We can now list contents of that container

![Image](https://github.com/user-attachments/assets/4a588849-70c6-4cfb-932d-a6ec75d18c0c)

- Attempt to upload

![Image](https://github.com/user-attachments/assets/8f9922e7-328f-4288-989b-53ea49202c84)

- Failed because we don’t have the needed credentials

![Image](https://github.com/user-attachments/assets/fe0b1396-c5f7-46a6-adc3-23009b507906)

4. Create third SAS with Write,Add,and Create permissions

![Image](https://github.com/user-attachments/assets/7fbc0de4-6670-481d-9a24-9209fb959542)

![Image](https://github.com/user-attachments/assets/cd14e0ed-f124-45c6-be9e-0f22c5eca317)

- Uploaded file successfully

![Image](https://github.com/user-attachments/assets/bab1e5db-c922-44a2-b1b2-f3406a7c7e22)

- Regenerate access keys to revoke access for the 3 access signatures

![Image](https://github.com/user-attachments/assets/2014ba3a-529e-413b-ab94-6b70ddfcbb97)

- Received the access deny error

![Image](https://github.com/user-attachments/assets/9364a400-ac69-4d23-9dfc-f0ad48930341)

5. Create a Stored Access Policy

![Image](https://github.com/user-attachments/assets/6869c4a4-154b-4475-9556-33a611f79fc9)

- Create a SAS from storage account

![Image](https://github.com/user-attachments/assets/0fa0f735-a224-4e61-bf09-fe83d9239ec4)

![Image](https://github.com/user-attachments/assets/5bfba568-4189-4bf7-b9cd-6b6028c2b572)

- Upload of file completed successfully

![Image](https://github.com/user-attachments/assets/62b298fd-eb09-45b8-be46-5466ea9feef1)

- Revoke Shared Access Signature (SAS) Access by Deleting the Stored Access Policy

![Image](https://github.com/user-attachments/assets/effeea35-66aa-484a-be0f-0e6d55eba457)

- Error message received confirming revocation

![Image](https://github.com/user-attachments/assets/70e4e2ec-5bdf-4434-a538-9b51cb8b5196)

