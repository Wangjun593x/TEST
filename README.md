# TEST
//#include "stdafx.h"
#include "stdio.h"
#include "ctype.h"
#include "string.h"
void main(void){
    char str[100],i,ln,ch;
    printf("Write an English sentence(less than 100 letters)...\n");
    i=ln=strlen(gets(str));
    while(!isalpha(str[--i]));
    ch=str[i+1];
    str[i+1]='\0';
    for(i=0;i<ln;i++)
        if(str[i]==' ') str[i]='\0';
    for(i=0;i<ln;i++)
        if(isalpha(str[i]) && (str[i-1]=='\0' || i==0)) 
            strrev(str+i);
    if(ch) str[i-1]=ch;
    for(i=0;i<ln;i++)
        if(str[i]=='\0') str[i]=' ';
    printf("%s\n",str);
}
