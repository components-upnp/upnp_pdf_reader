Lecteur PDF UPnP (pouvant être contrôlé par d'autres composants UPnP).

<strong>Installation:</strong>

Le repertoire build contient les éléments nécessaires pour éxecuter l'application: le fichier .jar et les dll
Il suffit de lancer le fichier .jar pour éxecuter l'application

Voici un exemple d'exécution de l'application:

![alt tag](https://github.com/components-upnp/upnp_pdf_reader/blob/master/CaptureLecteurPdf.PNG)

<strong>Specification UPnP:</strong>

Le device Lecteur PDF offre le service VisionneuseService, dont voici la description:

   1) SetTarget(String newTargetValue): newTargetValue pouvant être les chaînes DROITE ou GAUCHE respectivement pour avancer et reculer dans le défilement des slides.
   2) GetNbPages(): retourne le nombre de pages total du document ouvert (dans une variable ResultNbPages)
   3) GetNumPage(): retourne le numéro de la page courante (dans une variable ResultNumPage)
   
Ce composant envoie les événements:

   1) NumPage lorsque le numéro de la page courante a été changé
   2) NbPages lorsque le nombre de pages du documents a été changé
   3) StatusEvent lorsque une nouvelle direction est reçue.
  
Voici le schéma représentant le composant:

![alt tag](https://github.com/components-upnp/upnp_pdf_reader/blob/master/LecteurPDF.png)


<strong>Maintenance:</strong>

C'est un projet Maven
la librairie jmupdf n'a pas de depot Maven, il faut donc l'ajouter manuelement
Pour cela il suffit de copier le repertoire "jmupdf-core" dans le repository local Maven  
Effectuer les modifications souhaitées
Ajouter une configuration d'éxecution Maven avec la phase "package" pour exporter en .jar 
Executer cette commande; deux fichiers .jar sont crées dans un nouveau dossier target 
   Visionneuse-0.0.1-SNAPSHOT-jar-with-dependencies.jar qui est le bon éxecutable
   
   Visionneuse PDF utilise la librairie Java jmupdf(licence GPLv3) qui elle même est basée sur mupdf(licence AGPL) 
Le repertoire lib se trouvant à la racine du projet contient les dll de mupdf et le .jar de jmupdf(dans le repertoire jmupdf-core)
