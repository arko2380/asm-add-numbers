# asm-add-numbers
Adding Number In Assembly
.model small
.stack 100h
.data
msg db, 10, 13,'Enter a number$'
msg2 db 10, 13,'The sum is $'
x db ?
y db ?

.code
main proc
mov AX, @data
mov DS, AX
lea DX, msg
int 21h

mov AH, 1h 
int 21h

sub AL,'0'
mov x, AL

mov AH, 9h
lea DX, msg
int 21h

mov AH, 1h
int 21h

sub AL,'0'
mov y, AL
mov AH, 9h

lea DX, msg2
int 21h

mov DL, x
ADD DL, y
ADD DL,'0'
mov AH, 2h
int 21h

mov AH, 04ch
int 21h

main endp
end main
