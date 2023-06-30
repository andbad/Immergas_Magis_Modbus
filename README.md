# Immergas Magis Modbus
E' possibile leggere molti parametri di funzionamento e configurazione della pompa di calore Immergas Magis tramite protocollo Modbus RS-485.

# Collegamento
E' possibile collegarsi ai pin A/B sul retro del pannello di controllo 
![Schermata 2023-06-30 10:37:17](https://github.com/andbad/Immergas_Magis_Modbus/assets/7837288/6dfcf1fd-176e-4a37-a3d2-6790a0dac140)

Non è necessario utilizzare la massa (in ogni caso, è il morsetto E. Tra E e A/B ci sono 12V).
Ho utilizzato un normale adattatore RS-485 -> USB.

# Configurazione
Ho utilizzato l'applicazione qModMaster (https://github.com/zhanglongqi/qModMaster) configurata con i seguenti parametri per la comunicazione seriale:
Serial device: COM3 (dipende dalla porta in uso)
Serial Port: 1
Baud: 9600
Data Bits: 8
Stop Bits: 1
Parity: none
RTs: Disable
Slave Addr: 1

# Registri
Utilizzando i function code 0x03 ho rilevato la corrispondeza tra i valori dei registri e quelli impostati sul pannello di controllo.
Il formato dei registri è Decimale.

001 Attivo: 0 off, 2 on 
002 Modo funzionamento: 1 auto, 2 freddo, 3 caldo
012 Temperatura impostata su pannello (°C)
021 Consumo di energia (kWh)
103 Velocità ventilatore (rpm)
104 Apertura valvola espansione 
105 TW_0 Temp.Acqua IN SP (°C)
106 TW_0 Temp.Acqua OT SP (°C)
108 T4 Temp. Aria Esterna (°C)
109 temp scarico compr. 
110 temp asp compressora
113-114 temp refrigerante out/in
117 pressione compressore
120 tensione alimentazione V
123 tem. At. Tot. Comp ora
130 72 pompa di circolazione, 8264 pompa di calore, 0 spento
136 temp modulo tf
139 flusso acqua m3/h
145 consumo di energia kWh
/145 consumo di energia kWh/145 consumo di energia kWh
