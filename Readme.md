# Documentazione Login per Appraisal

Il server a dopo aver verificato la correttezza dei dati (email, passord, e tipoProfilo) ricevuti dal client genera una response e la invia.

La risposta che il client si aspetta è un oggetto JSON come questo.

```json
"data":{
        "AutenticationToken": "Stringa",
        "user_id": 1,
        "tipoProfilo": "Ruolo dell'utente"
    }
```

In questa risposta le chiavi sono:

- AutenticationToken ovvero una stringa che il server genera e che controlla ogni volta che il server invia una request
- user_id l'identificativo dell'utente, mi piacerebbe che la chiave sia questa
- tipoProfilo il quale e una stringa, da concordare se tutto maiuscolo o minuscolo.

I primi due parametri sono da riceversi obbligatoriamente, altrimenti l'applicazione mobile non ha modo di funzionare.
Il parametro tipoProfilo, non e necessario, è molto gradito in quanto sapendo quale utente sta loggando renderizzare lato app la giusta pagina.
Senza questo parametro sarei costretto a fare una get request in più al server, con le conseguenze del caso, oppure a rivedere con attenzione il _data Flow_ del'app.

Esempio di un eventuale risposta è visionabile nel file JSON è questo indirizzo [Appraisal](https://my-json-server.typicode.com/Aldodo91/Appraisal/data) 
