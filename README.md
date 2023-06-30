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
109 Tp Temp. Scarico compr. (°C)
110 Temp. Aspiraz. compr. (°C)
113 T2 Temp. Refr. Uscita SP (°C)
114 T2 Temp. Refr. In SP (°C)
117 P1 Pressione compr. (kPa)
120 Rensione alimentazione (V)
123 Tem. At. Tot. Comp (Hrs)
130 Pompa di circolazione attiva 72, Compressore attivo 8264, in standby 0
136 TF temp modulo (°C)
139 Flusso acqua (m3/h)
145 Consumo di energia (kWh)
