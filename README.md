# GestioneBatterieZigbeeXiaomiHANR

La gestione delle batterie dei vari dispositivi Zigbee e non tramite Nodered come integrazione di HomeAssistant

# Prerequisiti

Input number in home assistant chiamato input_number.notifica_low_battery
Subflow Iterate

# Come funziona

Questo flow gira 2 volte al giorno (paramentro impostabile dai 2 inject iniziali)
Fa un check di tutte le entità che finiscono per "_battery" (Valore modificabile tramite le espressioni regolari nel nodo get entities)
Per ogni entità trovata fa un check della batteria e lo confronta (tramite il primo switch) al valore da noi impostato su HA. 
Subito dopo nel mio caso ci sono 2 switch(opzionali) che mi hanno permesso di escludere le 2 entità che finiscono per _battery ma non vanno considerate.
Infine viene mandata una notifica tramte il nodo notify.

# Come importarlo

Da nodered andare sul menu in alto a destra e fare import. Importare quindi il file flows.json
Una volta fatto controllare nei nodi che il server homeassistant sia il vostro.
