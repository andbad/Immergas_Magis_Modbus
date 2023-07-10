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
