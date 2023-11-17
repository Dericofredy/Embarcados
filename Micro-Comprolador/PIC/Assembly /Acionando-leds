    ; Configuração dos registradores
    ORG 0x00
    GOTO Main

    ORG 0x04
Main:
    ; Configuração dos pinos como saídas para os LEDs
    BSF STATUS, RP0     ; Banco 1
    CLRF TRISB          ; Todos os pinos de RB como saídas
    BCF STATUS, RP0     ; Banco 0

Loop:
    ; Aciona os LEDs sequencialmente
    BSF PORTB, 0        ; Aciona o LED conectado a RB0
    CALL Delay          ; Chama a rotina de atraso
    BCF PORTB, 0        ; Desliga o LED
    CALL Delay

    BSF PORTB, 1        ; Aciona o LED conectado a RB1
    CALL Delay
    BCF PORTB, 1
    CALL Delay

    BSF PORTB, 2        ; Aciona o LED conectado a RB2
    CALL Delay
    BCF PORTB, 2
    CALL Delay

    BSF PORTB, 3        ; Aciona o LED conectado a RB3
    CALL Delay
    BCF PORTB, 3
    CALL Delay

    GOTO Loop

Delay:
    ; Rotina de atraso
    MOVLW D'100'        ; Valor para o contador
    MOVWF 0x20          ; Armazena o valor no registrador de trabalho
DelayLoop:
    DECFSZ 0x20, 1      ; Decrementa o contador
    GOTO DelayLoop      ; Salta se não zero
    RETURN
