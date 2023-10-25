Niveau facile:

Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ? 
346+1(de l'index0) la console le dit sans regarder l'id. Sinon si on aime on peux faire Album.count


Qui est l'auteur de la chanson "White Room" ?
Track.where(title:"White Room") ==> "Eric Clapton"


Quelle chanson dure exactement 188133 milliseconds ?
tp Track.where(size:188133) ==> aucune


Quel groupe a sorti l'album "Use Your Illusion II" ?
tp Album.where(title:"Use Your Illusion II") ==> "Guns n Roses"


Niveau Moyen:

Combien y a t'il d'albums dont le titre contient "Great" ?
Album.where("title LIKE ?", "%Great%").count => 13

Supprime tous les albums dont le nom contient "music".
Album.where("title LIKE ?", "%music%").all   // pas osé tester avec "Music" au lieux de "music"

Combien y a t'il d'albums écrits par AC/DC ?
Album.where(artist:"AC/DC").count => 2 // En soit nous n'avons pas les data d'Auteur-compositeur je suis donc partit du principe que l'artiste avais écrit son album ce qui n'est pas toujours le cas.

Combien de chanson durent exactement 158589 millisecondes
Track.where(size:158589).count => 0

Niveau Difficile:

puts en console tous les titres de AC/DC.
tp Track.where(artist:"AC/DC").each do |track| 
  track.title
end => un joli tableau avec les datas demandées


puts en console tous les titres de l'album "Let There Be Rock".
tp Track.where(album:"Let There Be Rock").each do |track|
  track.title
end => un joli tableau avec les datas demandées


Calcule le prix total de cet album ainsi que sa durée totale.
