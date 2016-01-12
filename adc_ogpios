/* 12 bits ADC lecture converted to 8 bits with output GPIO's
 * 
 * Code provided is as is,
 * not all functionality has been tested
 *
 */

#include <stdlib.h>
#include <stdio.h>
#include <signal.h>
#include <string.h>
#include <unistd.h>
#include <sys/stat.h>
#include <sys/types.h>
#include <sys/ioctl.h>
#include <sys/select.h>
#include <fcntl.h>
#include <math.h>


//ADC configuration: AlN0
#define SYSFS_ADC_DIR "/sys/bus/iio/devices/iio:device0/in_voltage0_raw"
#define MAX_BUFF 64     //This is plenty large


int mi_atoi(const char *cad, int tam);
int caracter_valido(const char caracter);
int readADC(unsigned int pin);
void reverse(char s[]);
void itoa(int n, char s[]);


int main(void) {
    
    int fd,k,q;
	char buf[MAX_BUFF];
	char ch[5];
	char ch2[5];
	char ch3[10];
	ch[4] = 0;

  
    
    //GPIOS used from MSB to LSB: GPIO_60, GPIO_30, GPIO_50, GPIO_31, GPIO_54, GPIO_48, GPIO_15, GPIO_49
    
    //exporting all GPIO's used:
    
    // export pin 1
    int GPIOPin=60, /* GPIO1_28 or pin 12 on the P9 header */ i=0;
 
    printf("\nStarting ADC_GPIO program\n");
    FILE *myOutputHandle = NULL;
    char setValue[4], GPIOString[4], GPIOValue[64], GPIODirection[64];
    sprintf(GPIOString, "%d", GPIOPin);
    sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
    sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
    
    // Export the pin 
    if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
        printf("Unable to export GPIO pin\n");
        return 1;
    }
    
    strcpy(setValue, GPIOString);
    fwrite(&setValue, sizeof(char), 2, myOutputHandle);
    fclose(myOutputHandle);
 
    // Set direction of the pin to an output
     if ((myOutputHandle = fopen(GPIODirection, "rb+")) == NULL){
        printf("Unable to open direction handle\n");
        return 1;
    }
    
    strcpy(setValue,"out");
    fwrite(&setValue, sizeof(char), 3, myOutputHandle);
    fclose(myOutputHandle);
    
    
    // export pin 2
    GPIOPin=50;
    sprintf(GPIOString, "%d", GPIOPin);
    sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
    sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
    
    // Export the pin
    if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
        printf("Unable to export GPIO pin\n");
        return 1;
    }
    
    strcpy(setValue, GPIOString);
    fwrite(&setValue, sizeof(char), 2, myOutputHandle);
    fclose(myOutputHandle);
 
    // Set direction of the pin to an output
     if ((myOutputHandle = fopen(GPIODirection, "rb+")) == NULL){
        printf("Unable to open direction handle\n");
        return 1;
    }
    
    strcpy(setValue,"out");
    fwrite(&setValue, sizeof(char), 3, myOutputHandle);
    fclose(myOutputHandle);
    
    // export pin 3
     GPIOPin=30;
    sprintf(GPIOString, "%d", GPIOPin);
    sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
    sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
    
    // Export the pin
    if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
        printf("Unable to export GPIO pin\n");
        return 1;
    }
    
    strcpy(setValue, GPIOString);
    fwrite(&setValue, sizeof(char), 2, myOutputHandle);
    fclose(myOutputHandle);
 
    // Set direction of the pin to an output
     if ((myOutputHandle = fopen(GPIODirection, "rb+")) == NULL){
        printf("Unable to open direction handle\n");
        return 1;
    }
    
    strcpy(setValue,"out");
    fwrite(&setValue, sizeof(char), 3, myOutputHandle);
    fclose(myOutputHandle);
    
    // export pin 4
     GPIOPin=31;
    sprintf(GPIOString, "%d", GPIOPin);
    sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
    sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
    
    // Export the pin
    if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
        printf("Unable to export GPIO pin\n");
        return 1;
    }
    
    strcpy(setValue, GPIOString);
    fwrite(&setValue, sizeof(char), 2, myOutputHandle);
    fclose(myOutputHandle);
 
    // Set direction of the pin to an output
     if ((myOutputHandle = fopen(GPIODirection, "rb+")) == NULL){
        printf("Unable to open direction handle\n");
        return 1;
    }
    
    strcpy(setValue,"out");
    fwrite(&setValue, sizeof(char), 3, myOutputHandle);
    fclose(myOutputHandle);
    
    // export pin 5
     GPIOPin=51;
    sprintf(GPIOString, "%d", GPIOPin);
    sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
    sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
    
    // Export the pin
    if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
        printf("Unable to export GPIO pin\n");
        return 1;
    }
    
    strcpy(setValue, GPIOString);
    fwrite(&setValue, sizeof(char), 2, myOutputHandle);
    fclose(myOutputHandle);
 
    // Set direction of the pin to an output
     if ((myOutputHandle = fopen(GPIODirection, "rb+")) == NULL){
        printf("Unable to open direction handle\n");
        return 1;
    }
    
    strcpy(setValue,"out");
    fwrite(&setValue, sizeof(char), 3, myOutputHandle);
    fclose(myOutputHandle);
    
    
    // export pin 6
     GPIOPin=48;
    sprintf(GPIOString, "%d", GPIOPin);
    sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
    sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
    
    // Export the pin
    if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
        printf("Unable to export GPIO pin\n");
        return 1;
    }
    
    strcpy(setValue, GPIOString);
    fwrite(&setValue, sizeof(char), 2, myOutputHandle);
    fclose(myOutputHandle);
 
    // Set direction of the pin to an output
     if ((myOutputHandle = fopen(GPIODirection, "rb+")) == NULL){
        printf("Unable to open direction handle\n");
        return 1;
    }
    
    strcpy(setValue,"out");
    fwrite(&setValue, sizeof(char), 3, myOutputHandle);
    fclose(myOutputHandle);
    
    
    // export pin 6
     GPIOPin=15;
    sprintf(GPIOString, "%d", GPIOPin);
    sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
    sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
    
    // Export the pin
    if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
        printf("Unable to export GPIO pin\n");
        return 1;
    }
    
    strcpy(setValue, GPIOString);
    fwrite(&setValue, sizeof(char), 2, myOutputHandle);
    fclose(myOutputHandle);
 
    // Set direction of the pin to an output
     if ((myOutputHandle = fopen(GPIODirection, "rb+")) == NULL){
        printf("Unable to open direction handle\n");
        return 1;
    }
    
    strcpy(setValue,"out");
    fwrite(&setValue, sizeof(char), 3, myOutputHandle);
    fclose(myOutputHandle);
    
    // export pin 8
     GPIOPin=49;
    sprintf(GPIOString, "%d", GPIOPin);
    sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
    sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
    
    // Export the pin
    if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
        printf("Unable to export GPIO pin\n");
        return 1;
    }
    
    strcpy(setValue, GPIOString);
    fwrite(&setValue, sizeof(char), 2, myOutputHandle);
    fclose(myOutputHandle);
 
    // Set direction of the pin to an output
     if ((myOutputHandle = fopen(GPIODirection, "rb+")) == NULL){
        printf("Unable to open direction handle\n");
        return 1;
    }
    
    strcpy(setValue,"out");
    fwrite(&setValue, sizeof(char), 3, myOutputHandle);
    fclose(myOutputHandle);
    
    //end GPIOS
    
    


    while(1) {
        
        printf("ADC value with 12 bits:\n");
        
        //Reading the ADC file:
        snprintf(buf, sizeof(buf), SYSFS_ADC_DIR);
        fd=open(buf, O_RDONLY);
        read(fd,ch,4);
        close(fd);
        
        //Converting ADC value to int:
        k=mi_atoi(ch, strlen(ch));
        printf("%d\n",k);
        
        //12 bit convertion to 8 bit
        q=(k*255)/4095;
        
        printf("ADC value with 8 bits:\n");
        printf("%d\n",q);
        
        
        //Configuration of GPIO outputs depending of the 8 bit ADC value:
        if(q>=128){
            
            q=q-128;
            GPIOPin=60;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL)   {
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
       
            // Set output to high
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
            }
        
            strcpy(setValue, "1"); // Set value high
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
            //sleep(1); // wait for 1 sec
        }
        else{
            GPIOPin=60;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
        
            // Set output to low
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
        
            }
            strcpy(setValue, "0"); // Set value low
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
        }
         
        if(q>=64){
            
            q=q-64;
            GPIOPin=30;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL)   {
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
       
            // Set output to high
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
            }
        
            strcpy(setValue, "1"); // Set value high
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
            //sleep(1); // wait for 1 sec
        }
        else{
            GPIOPin=30;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
        
            // Set output to low
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
        
            }
            strcpy(setValue, "0"); // Set value low
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
        }
         //printf("%d\n",q);
        if(q>=32){
            
            q=q-32;
            GPIOPin=50;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL)   {
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
       
            // Set output to high
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
            }
        
            strcpy(setValue, "1"); // Set value high
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
            //sleep(1); // wait for 1 sec
        }
        else{
            GPIOPin=50;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
        
            // Set output to low
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
        
            }
            strcpy(setValue, "0"); // Set value low
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
        }
         //printf("%d\n",q);
        if(q>=16){
            
            q=q-16;
            GPIOPin=31;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL)   {
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
       
            // Set output to high
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
            }
        
            strcpy(setValue, "1"); // Set value high
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
            //sleep(1); // wait for 1 sec
        }
        else{
            GPIOPin=31;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
        
            // Set output to low
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
        
            }
            strcpy(setValue, "0"); // Set value low
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
        }
        
        if(q>=8){
            
            q=q-8;
            GPIOPin=51;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL)   {
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
       
            // Set output to high
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
            }
        
            strcpy(setValue, "1"); // Set value high
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
            //sleep(1); // wait for 1 sec
        }
        else{
            GPIOPin=51;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
        
            // Set output to low
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
        
            }
            strcpy(setValue, "0"); // Set value low
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
        }
        
        if(q>=4){
            
            q=q-4;
            GPIOPin=48;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL)   {
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
       
            // Set output to high
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
            }
        
            strcpy(setValue, "1"); // Set value high
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
            //sleep(1); // wait for 1 sec
        }
        else{
            GPIOPin=48;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
        
            // Set output to low
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
        
            }
            strcpy(setValue, "0"); // Set value low
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
        }
        
        if(q>=2){
            
            q=q-2;
            GPIOPin=15;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL)   {
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
       
            // Set output to high
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
            }
        
            strcpy(setValue, "1"); // Set value high
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
            //sleep(1); // wait for 1 sec
        }
        else{
            GPIOPin=15;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
        
            // Set output to low
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
        
            }
            strcpy(setValue, "0"); // Set value low
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
        }
        
        //printf("%d\n",q);
        if(q>=1){
            
            q=q-1;
            GPIOPin=49;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL)   {
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
       
            // Set output to high
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
            }
        
            strcpy(setValue, "1"); // Set value high
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
            //sleep(1); // wait for 1 sec
        }
        else{
            GPIOPin=49;
        
            sprintf(GPIOString, "%d", GPIOPin);
            sprintf(GPIOValue, "/sys/class/gpio/gpio%d/value", GPIOPin);
            sprintf(GPIODirection, "/sys/class/gpio/gpio%d/direction", GPIOPin);
        
            if ((myOutputHandle = fopen("/sys/class/gpio/export", "ab")) == NULL){
                printf("Unable to export GPIO pin\n");
                return 1;
            }
       
            strcpy(setValue, GPIOString);
            fwrite(&setValue, sizeof(char), 2, myOutputHandle);
            fclose(myOutputHandle);
        
            // Set output to low
            if ((myOutputHandle = fopen(GPIOValue, "rb+")) == NULL){
                printf("Unable to open value handle\n");
                return 1;
        
            }
            strcpy(setValue, "0"); // Set value low
            fwrite(&setValue, sizeof(char), 1, myOutputHandle);
            fclose(myOutputHandle);
        }
        
        
        
        //final part GPIO
        
        if ((myOutputHandle = fopen("/sys/class/gpio/unexport", "ab")) == NULL) {
        printf("Unable to unexport GPIO pin\n");
        return 1;
        }
        
        fclose(myOutputHandle);

                    sleep(1);
                    
                    
    
    
    }

    return 0;
}

int caracter_valido(const char cad)
{
    return cad >= '0' && cad <='9';
}

int mi_atoi(const char *cad, int tam)
{
    int i=tam-1, entero=0, pos=1;
    while (i>=0)
    {
        while (caracter_valido(cad[i]))
        {
            entero=entero+(cad[i]-48)*pos;
            pos=pos*10;
            i--;
        }
    pos =1;
    i--;
    }
    return entero;
}
