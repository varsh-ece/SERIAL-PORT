
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H
MOV TMOD,#20H
MOV TH1,#0FDH
MOV SCON,#40H
SETB TR1
MOV SBUF ,#'B'
WAIT:JNB TI,WAIT
CLR TI
END

```
### (ii) Serial Port to Transfer a Message

```
ORG 00H
MOV DPTR,#4500H
MOV TMOD,#20H
MOV TH1,#0FDH
MOV SCON,#40H
SETB TR1
AGAIN:MOVX A,@DPTR
MOV SBUF,A
WAIT:JNB TI,WAIT
CLR TI
INC DPTR
SJMP AGAIN
END


```

### OUTPUT:
<img width="1358" height="544" alt="Screenshot 2025-10-15 074508" src="https://github.com/user-attachments/assets/a65f5e0c-d552-4688-8b83-f407d6b9dd8e" />
<img width="1468" height="779" alt="Screenshot 2025-10-15 081948" src="https://github.com/user-attachments/assets/d4bf49fe-a96e-4aff-a4db-14c7a7afef34" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
