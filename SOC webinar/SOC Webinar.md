# SOC Webinar
Amr Ashraf
Metodo di investigazione di allerte: vedere child process, parent process, cambio di registri, connessioni esterne
Una minaccia per una impresa, non implica che sia una minaccia per tutte le imprese

## HEATMAP
mitre-attack.github.io/attack-navigator/
come capire quali tecniche condividino le APT che sono interessate nella nostra impresa, usare la pagina di prima e utilizzare un "layer from others layers" per sovrapporre le diverse tecniche utilizzate dalle diverse APT.

DeTT&CT github->clonare il repositorio -> pip install -r requirements.txt
generic -ds esce una lista de DataSources utilizzabili
con il yaml uscito, é possibile metterlo nel sito di mitre-attack-navigator per ottenere una heatmap python ./detect.py ds -fd 'file' -l viene creato un JSON file nella cartella output
importa il JSON per ricevere la heatmap con gli scores, ti da un numero che ti permette capire quanto hai coperto un certo attacco in base a ció che controlli


DOMANDA: come riconoscere se si é attaccati da un gruppo o APT specifica?
piu per threat intelligence. APT MAP github cerca le APT che possono targettare i filtri che utilizzi, utilizza open source information e da un descrizione data da altre imprese