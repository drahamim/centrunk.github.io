# Keyloading a Motorola radio
## APX Series (Software Key loading)
### Prerequisites
- APX CPS 
- Programming Cable
- [KFDTool](https://github.com/omahacommsys/KFDtool/releases/latest)
- Radio Feature Sets (either combination is supported, however you will be limited to the algorithm(s) in your flashcode).
    - QA06653	SW-AES
    - QA07949	DES Software Crypto
    - Q667      Advanced Digital Privacy
### CPS Configuration
#### Secure Configuration > Secure Wide
- General:
    - Secure Operation: `Software`
    - *Secure Algorithms*:
        - Check the boxes for the algorithms you will be loading (as available in the radio's flashcode)
    - Keyloading Source: `KVL`
- Encryption Key List:
    - Create as many rows matching the number of keys you will be loading
    - Key Name should match the keys you will be loading for easy identification
    - CKR# needs to be the Decimal format value
#### Trunking Configuration > Trunking Personality
Select the Personality that contains the Talkgroups you will be assigning the keys to.

- Talkgroup *Per talkgroup*
    - Secure / Clear Strapping: `Select` or `Secure` depending on your system's requirements
    - Key Select: `<Assign your key>`

### KFDTool Configuration
#### Multi Key Load
Make sure you have your .ekc file

Steps:

1. Download KFDTool from the above link
2. Unzip the compressed file (No installation needed)
3. Connect your APX Radio via USB programming cable
4. Select Container > Open
- Navigate to your downloaded .ekc file and open it. 
5. (Optional) Enter the password for your file.
6. Select P25 KFD > Multiple Keyload from the top navigation bar
7. Select the keys from the "Available" list and click add 
8. Click Load.
7. Your radio should beep momentarily and then reboot. 

*CONGRATS* you have loaded keys.

TROUBLESHOOTING:

*If you receive a key length error check the following* 

- Do you have the same number of entries in the table s the number of keys you plan to load. 
- Is the CKR correct for your keys 