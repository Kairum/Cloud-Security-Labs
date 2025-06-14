1. Assign a policy to block the deployment of resource groups when a Cost Allocation tag is not provided.
   a.	Choose policy definition
   
   ![Image](https://github.com/user-attachments/assets/7786cfb3-bbfe-4fe4-961f-b9fbd4412abb)

   b. Create tag name

   ![Image](https://github.com/user-attachments/assets/e9121b22-2d15-4f21-a044-df8203107428)

   c. Create Non-compliance message

   ![Image](https://github.com/user-attachments/assets/f3f5f478-4d8e-484a-99cc-b92b6b73810f)

   d. Policy created
   
   ![Image](https://github.com/user-attachments/assets/3910c58f-345f-4f48-8f4e-f26aa551fe4f)

2. Create a second policy
   a. Second policy will inherit a tag from the resource group if its missing

   ![Image](https://github.com/user-attachments/assets/de8d5bee-c61c-4b87-b032-8d11aa43bc19)

   b. Associate the existing user-assigned managed identity with the policy assignment

   ![Image](https://github.com/user-attachments/assets/2a58736d-55e9-44e8-ad90-cf6f5168dfc6)

   c. Policy created

   ![Image](https://github.com/user-attachments/assets/31dd7cc6-4246-49dd-ba73-5ac5e59a259a)

3. Create Cost Allocation tag

![Image](https://github.com/user-attachments/assets/6eb03779-2fc5-473b-bfb9-4eb54cba051b)

4. Create new Vnet with no cost allocation tag

![Image](https://github.com/user-attachments/assets/6f078333-3c5f-4c4e-8080-7fa580216594)

5. We see PolicyVnet2 inherited the tag from the resource group

![Image](https://github.com/user-attachments/assets/1e4a5f01-d080-446d-942d-33de2a1a8d3e)

6. Looking back at PolicyVnet1, we can see it still has no tags

![Image](https://github.com/user-attachments/assets/0c2d1f99-5286-4c85-8178-1f9e7b988b87)

7. Create a remediation task to bring the existing virtual network into compliance.

![Image](https://github.com/user-attachments/assets/f865403f-dd45-463a-857c-55ec834b4040)

8. Remediation task completed

![Image](https://github.com/user-attachments/assets/58521f83-c555-4cba-9f94-a5046c0e21ba)

9. The remediation task has inherited the cost allocation tag from the resource group to PolicyVnet1

![Image](https://github.com/user-attachments/assets/50ca61dc-dd71-4d1d-93d7-a71ae886dac6)
   
   



   
       
