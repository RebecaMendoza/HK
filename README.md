# HK
Funcionamiento de HK 
## Comandos principales

1. Initial configuration
2. Montaje memoria SD
3. Reset ++ (*conteo de cuántas veces entra el reset*)
4. Leer Reset
5. Variable Reset > 1  *si cumple*  Ver UMBRAL CHECK > UB  *si cumple* VCC1 UMBRAL CHECK > VS *si cumple* Inicia modo NORMAL	
    
    Variable Reset > 1  *si cumple*  Ver UMBRAL CHECK > UB  *si no cumple*  TIMER 1 HR y regresa a Montaje memoria SD

 	Variable Reset > 1  *si cumple*  Ver UMBRAL CHECK > UB  *si cumple* VCC1 UMBRAL CHECK > VS *si no cumple*  Inicia modo SAFE
             
### NORMAL

1. Encender relevadores
2. F=1/59 y DELTA T=0 Habilita inteeruptor timer TELECOMUNICACION / UART OBC
3. VCC1 CHECK
4. VCC1 > VS

*si cumple* regresa a F=1/59 y DELTA T=0 Habilita inteeruptor timer TELECOMUNICACION / UART OBC  *si no cumple* Inicia modo SAFE
    
### SAFE

1. Apagar relevadores 
2. Desactivar interruptores de meassure y comunicación con OBC
3. VCC1 CHECK
4. VCC1 > VS

*si cumple* Inicia modo NORMAL *si no cumple* regresa a Desactivar interruptores de meassure y comunicación con OBC

#### Envío (Interruptor)

1. MF_OBC
*si cumple 0*
a) Leer Tele.txt
b) Enviar a OBC
 c) Apuntador ++
  d) END OF FILE
*si cumple* Apuntador = 0 *si no cumple* END

*si cumple 1*
a) Leer IMU.txt
b) Enviar a OBC
c) Apunt ++
d) END OF FILE
*si cumple* Apunt= 0 *si no cumple* END
