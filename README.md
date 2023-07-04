# Immergas Magis Modbus
E' possibile leggere molti parametri di funzionamento e configurazione della pompa di calore Immergas Magis tramite protocollo Modbus RS-485.

# Collegamento
E' possibile collegarsi ai pin A/B sul retro del pannello di controllo 
![Schermata 2023-06-30 10:37:17](https://github.com/andbad/Immergas_Magis_Modbus/assets/7837288/6dfcf1fd-176e-4a37-a3d2-6790a0dac140)

Non è necessario utilizzare la massa (in ogni caso, è il morsetto E. Tra E e A/B ci sono 12V).
Ho utilizzato un normale adattatore RS-485 -> USB.

# Configurazione
Ho utilizzato l'applicazione qModMaster (https://github.com/zhanglongqi/qModMaster) configurata con i seguenti parametri per la comunicazione seriale:<br>
Serial device: COM3 (dipende dalla porta in uso)<br>
Serial Port: 1<br>
Baud: 9600<br>
Data Bits: 8<br>
Stop Bits: 1<br>
Parity: none<br>
RTs: Disable<br>
Slave Addr: 1<br>

# Registri
Utilizzando i function code 0x03 ho rilevato la corrispondeza tra i valori dei registri e quelli impostati sul pannello di controllo.<br>
Il formato dei registri è Decimale.<br>
<br>
001 Attivo: 0 off, 2 on <br>
002 Modo funzionamento: 1 auto, 2 freddo, 3 caldo<br>
012 Temperatura impostata su pannello (°C)<br>
021 Consumo di energia (kWh)<br>
103 Velocità ventilatore (rpm)<br>
104 Apertura valvola espansione <br>
105 TW_0 Temp.Acqua IN SP (°C)<br>
106 TW_0 Temp.Acqua OT SP (°C)<br>
108 T4 Temp. Aria Esterna (°C)<br>
109 Tp Temp. Scarico compr. (°C)<br>
110 Temp. Aspiraz. compr. (°C)<br>
113 T2 Temp. Refr. Uscita SP (°C)<br>
114 T2 Temp. Refr. In SP (°C)<br>
117 P1 Pressione compr. (kPa)<br>
120 Tensione alimentazione (V)<br>
123 Tem. At. Tot. Comp (Hrs)<br>
130 Pompa di circolazione attiva 72, Compressore attivo 8264, in standby 0<br>
136 TF temp modulo (°C)<br>
139 Flusso acqua (m3/h)<br>
145 Consumo di energia (kWh)<br>
<br>
