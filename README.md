# Configuring-Active-Directory-in-Azure

# Environments and Technology used
 - Microsoft Azure
 - Remote Desktop
 - Active Directory Domain Services
 - Powershell

![Screenshot (58)](https://github.com/user-attachments/assets/50df7b90-8bc5-467b-b7d5-5dfad659448a)


![Screenshot (59)](https://github.com/user-attachments/assets/c9c0daa1-9a87-4729-ab22-2314286a89de)


![Screenshot (60)](https://github.com/user-attachments/assets/b71eef45-b6a2-4c4c-8443-1c349711a24f)


![Screenshot (61)](https://github.com/user-attachments/assets/445eeceb-90dd-408f-aa00-a3967c4af8aa)


![Screenshot (62)](https://github.com/user-attachments/assets/02814362-1a3e-47aa-afe3-3294bdfb1750)

In these past 5 screenshots, I manually configured The NIC private IP address in Azure to static so that it wouldn't change when the virtual machine restarts and it would stay in sync with the client remote desktop.

## Navagating Active Directory
![Screenshot (63)](https://github.com/user-attachments/assets/3a63e41e-47a9-4205-8d8e-1ea1063d9967)


![Screenshot (64)](https://github.com/user-attachments/assets/0d5b8194-12c2-41e8-8517-300e20287dc8)
I Created 2 new organaztional units _EMPLOYEES and _ADMINS

![Screenshot (65)](https://github.com/user-attachments/assets/7965447b-7c16-443e-82b2-8def7ddc058d)


![Screenshot (67)](https://github.com/user-attachments/assets/f241b950-c6d1-4c54-9819-f73252f77267)
I created a new user named Jane Doe in Active Directory

![Screenshot (68)](https://github.com/user-attachments/assets/4df82529-02c1-49d5-af28-49fb4fce2c82)
I added her to the group Domain Admins to give full access with no restraints for when I login into the domain controller as the user

![Screenshot (69)](https://github.com/user-attachments/assets/5190640c-e3fc-4684-aaaa-f266b7f31aea)
I logged in as Jane Doe


![Screenshot (70)](https://github.com/user-attachments/assets/3bd98434-3014-42d1-a9b6-98d322e8456f)
I joined Client-1 VM to the same domain as the Active Directory vm dc-1

![Screenshot (71)](https://github.com/user-attachments/assets/44798432-bf59-49ea-8fc4-4d9fd13822ef)
Client 1 is now in the same domain as the Domain Controller and is now one of the computers in the domain.


![Screenshot (74)](https://github.com/user-attachments/assets/2fa12f2b-fc76-462a-99c8-438a7a4f39ec)


![Screenshot (75)](https://github.com/user-attachments/assets/42840670-c5a6-4935-adf4-40bd00d6b939)
Here I double checked if Jane Doe had full access to the Domain Users Group.

![Screenshot (76)](https://github.com/user-attachments/assets/d0220526-b8d7-4cfd-b1ae-65d0cf3d58fd)


![Screenshot (77)](https://github.com/user-attachments/assets/7c6cba63-207d-4bb8-81be-d7a7d1c983b8)
I used a code in powershell to create random users in the employees folder in active directory.

![Screenshot (78)](https://github.com/user-attachments/assets/57bc53b5-4db3-48d5-a260-55d9302cfa5e)
I selected a random user to log into client 1 with nuq.qic

![Screenshot (79)](https://github.com/user-attachments/assets/e2525310-e466-4069-bdc4-56a336c9d83e)



![Screenshot (80)](https://github.com/user-attachments/assets/f46a32c7-d621-4a55-b10b-f89b76d000be)
I updated the account lockout duration properties to being locked out for 30 minutes ater 5 attempts.

![Screenshot (81)](https://github.com/user-attachments/assets/ead10667-0dc0-4459-8798-7ace20cbe5a1)
I wanted to verify the policy was updated.

![Screenshot (82)](https://github.com/user-attachments/assets/11751fff-98f7-446d-bc09-832884a6873a)
I forced the policy to update just in case it didn't

![Screenshot (83)](https://github.com/user-attachments/assets/418d5d11-2f50-49fd-a6b6-5957c8b2858d)
I tested the policy myself and locked out a different random user bib.box

![Screenshot (84)](https://github.com/user-attachments/assets/6a90e0af-5ba2-48e1-bcec-bb029e17e431)
I changed the policy in Active Directory so the password never expired.

![Screenshot (86)](https://github.com/user-attachments/assets/282b6a96-e2e4-4ceb-b5e0-32b179bf6510)
I set a new password and unlocked the users account 


![Screenshot (87)](https://github.com/user-attachments/assets/c3f5424f-b876-44df-92a2-64587c0dc775)
Password was successfully changed

![Screenshot (88)](https://github.com/user-attachments/assets/472d58d6-d931-4b65-a5c0-648849a8de28)
I disabled bib.box just to teach myself how to do so.

![Screenshot (89)](https://github.com/user-attachments/assets/8940b7d1-9748-462e-8bf4-d09a435b1f4b)
I tried to log in, just to test out if I successfully did so.

![Screenshot (90)](https://github.com/user-attachments/assets/99dc2b39-7248-4c35-ba2b-53cffa357e14)
I re-enabled the account.


## Understanding DNS in Active Directory
![Screenshot (92)](https://github.com/user-attachments/assets/b16c24d0-5cb5-4f68-9d0c-55efa1c9e92d)
Here I looked up the hosts file in the Drivers folder, located in the Systems folder.
![Screenshot (93)](https://github.com/user-attachments/assets/2b886c5d-401f-427f-8d0c-9dafc3ed765c)
Here I'm assigning the IP address to the name mainframe and creating a new host for it.

![Screenshot (94)](https://github.com/user-attachments/assets/83856d8b-1b65-42af-8d00-9ad74bf46619)
You can see the new host mainframe in the DNS Manager list

![Screenshot (95)](https://github.com/user-attachments/assets/d8d3a36b-d884-4486-b66f-f125c4af7a8d)
 I pinged the new host named mainframe and the ping was successful

![Screenshot (96)](https://github.com/user-attachments/assets/c6f9f647-e0d0-4004-b9fe-0ac46aa33f49)
I changed the IP address record to 8.8.8.8


![Screenshot (97)](https://github.com/user-attachments/assets/9648882e-283f-43d3-b989-01ebe801e9c9)
After changing it I noticed that the IP address still says 10.0.0.4

![Screenshot (98)](https://github.com/user-attachments/assets/7d72d5cf-ba6a-4f5b-b572-b73ab4600eb8)
I noticed that when I pinged it is an administrator it showed the real IP address which was 8.8.8.8, this taught me that the Regular users have different access' than administrators, including seeing the real IP address.

![Screenshot (99)](https://github.com/user-attachments/assets/e8bf3dbb-449d-48a2-a246-a1cae3bd6fc3)
I created a new host named wengleski and assigned it to google.


![Screenshot (101)](https://github.com/user-attachments/assets/e2f45583-70d7-4f38-8578-219292e733a1)
I pinged wengleski and it pinged google and the IP address assigned to google. I then used nslookup, the IP address showed up along with the name and google's IP address. 

## Managing Users In Active Directory
![Screenshot (102)](https://github.com/user-attachments/assets/720a741a-eb87-4315-bfda-087883fa92ee)
I looked  up a user from the empoloyee folder and I changed the password.


![Screenshot (103)](https://github.com/user-attachments/assets/ed77a490-a928-4105-989e-f0bf43222b93)
I shared the folder Network Access with Domain Users

![Screenshot (104)](https://github.com/user-attachments/assets/8080a4fd-f0b4-44f3-b894-d357fe47a044)
I was successfully able to share the folder with the Domain Users

![Screenshot (105)](https://github.com/user-attachments/assets/9fd46938-7a48-4032-a5eb-1c30e936db91)
I'm showing that the address permissions have successfully changed. Now it displays Read/Write instead of just read

![Screenshot (111)](https://github.com/user-attachments/assets/76dab9a6-af38-4f63-98bd-ca20a8764b37)
Here I'm observing the group ACCOUNTANTS

![Screenshot (112)](https://github.com/user-attachments/assets/114e8dfa-4be4-4502-b573-729dce7fbf76)


![Screenshot (113)](https://github.com/user-attachments/assets/2aeeb788-3faa-4f32-a20c-a5e32fb837b5)

![Screenshot (114)](https://github.com/user-attachments/assets/df69beb4-3930-4fc0-929c-b4373278c912)
I Shared the folder with with Jane Doe, now it has read/write permissions

![Screenshot (115)](https://github.com/user-attachments/assets/4abe5f7d-615c-4679-91d0-7176968c9b0d)
THe folder was successfully shared.

![Screenshot (116)](https://github.com/user-attachments/assets/294ffc9b-bafd-488d-9c4c-45ddac7fc213)
I Added the user bad.qexi to the ACCOUNTANTS group so I can access the folder from the client-1 remote desktop where I logged in as bad.qexi


![Screenshot (117)](https://github.com/user-attachments/assets/82ba3b37-f94e-4b99-a516-5823d94f8ca3)
Here I have full access to the folder from the client-1 Virtual Machine after I gave myself access through Active Directory.
