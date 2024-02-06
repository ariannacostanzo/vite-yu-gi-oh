Ciao ragazzi!
Esercizio di oggi: Pokévuex
nome repo: vite-yu-gi-oh (sì, è proprio così, non preoccupatevi)
Descrizione:
Create un nuovo progetto utilizzando Vite e Vue 3 e definite i componenti necessari per strutturare un layout a tema Pokémon.
Al caricamento della pagina, effettuate una chiamata all'API di Pokémon
Cerchiamo di utilizzare lo store management per prenderci confidenza(nelle slide trovate anche codice di supporto, sfruttatele )
Qui trovate la documentazione: https://documenter.getpostman.com/view/1276443/2s8ZDbVLPF
NOTE
usate Postman per studiare la risposta!! (link a postman allegato)
Vi allego uno screen di una mia vecchia App Pokemon dalla quale potete trarre spunto per la grafica
Se qualche immagine non dovesse funzionare  non preoccupatevene troppo(ma mettete gli alt!)
Con i dati restituiti, stampate una card per ogni Pokémon.
BONUS: Creare un componente loader da visualizzare fino a quando i risultati non siano pronti.
Buon lavoro e gotta catch'em all! :pokeball:  */

@qui Ciao ragazzi,
Esercizio di oggi: Pokévue
nome repo: (stessa di ieri)
Continuiamo a lavorare sul nostro Pokedex, aggiungendo però un filtro di ricerca:
Il filtro deve essere fatto con una tendina <select> e deve permettere all'utente di filtrare i pokemon per tipo.
Per conoscere quali tipi sono disponibili, effettuate una chiamata via Postman all'indirizzo https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1 .
Copiate manualmente l'array che vi arriverà come risposta da Postman e usatelo per produrre dinamicamente le <options>.
Quando l'utente cambia il valore della tendina, potete usare il valore scelto per fare partire la chiamata API e mostrare i risultati in pagina!
Come faccio a sapere come filtrare? Bisogna guardare la documentazione:
https://documenter.getpostman.com/view/1276443/2s8ZDbVLPF#31f11fae-574f-4ac4-8882-c235058f517e
PS: non dimenticate di dare all'utente la possibilità di annullare il filtro e tornare alla chiamata "normale".
BONUS VARI:
Provare ad inserire i tipi chiamandoli direttamente dalle API e passandoli al componente della tendina.
Provare a inserire una paginazione (bisogna studiare bene i dati forniti dalla risposta delle API)
Provare ad aggiungere anche un filtro di tipo text per cercare tramite il nome dei pokemon!
Gotta catch'em all! :pikachu: