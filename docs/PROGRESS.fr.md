# Avancement du développement

[Retour au projet](../README.fr.md) · [English](PROGRESS.md)

Priorité : **reconstruction de l’environnement M.I.S.T.**, avec un **laboratoire Aya** séparé pour le personnage jouable. Cette vitrine de développement ne constitue pas une validation de version finale.

| Partie | État actuel |
| --- | --- |
| Espaces du M.I.S.T. | Stand de tir, salle de surveillance, sas-vestibule, couloir de service, zone d’accès restreint et armurerie, parking souterrain reconstruits aux cadrages d’origine ; nouvelles passes de détail à venir ; [point du 20 octobre](#mist-destruction-et-akropolis--point-du-20-octobre-2026) |
| Akropolis | Cartographiée et reconstruite en structure praticable (17 zones, 20 portes fonctionnelles) ; première passe de décor sur la promenade, la chapelle et le belvédère ; matières et éclairage à venir |
| Réactions environnementales | Intégrées au prototype ; destruction pièce par pièce des armoires d’armes, d’un mur carrelé et de l’extincteur, testée dans le moteur ; performances sous forte charge encore à travailler |
| Sauvegarde complète de partie | Non terminée |
| Laboratoire Aya (personnage jouable) | Expérimental, dans un projet Unreal séparé : déplacements, posture, visée, prise du pistolet, rechargement à vide et réactions au tir fonctionnent à différents niveaux ; le rechargement tactique et l’inspection courte restent à adapter ; [détails plus bas](#le-laboratoire-aya--point-du-12-octobre-2026) |
| Personnages définitifs | Non intégrés ; le laboratoire utilise une base provisoire, et l’apparence définitive d’Aya est encore en recherche |
| Textes anglais et français | Langues prévues ; couverture encore à vérifier |
| Version jouable publique | Aucune incluse dans cette vitrine |

Le travail avance par passes : construire, comparer, tester, puis corriger. Les captures montrent l’état visuel d’une version donnée ; leur définition ne constitue pas une mesure de performance à cette résolution.

Aucune date de sortie n’est annoncée. Les voix, les cinématiques et l’extension au-delà des espaces actuels restent des pistes pour la suite.

## M.I.S.T., destruction et Akropolis — point du 20 octobre 2026

Le **M.I.S.T.** va maintenant au-delà du sas : le couloir de service, la porte de la zone d’accès restreint et son digicode, l’armurerie derrière sa cage grillagée, et le parking souterrain. Chaque espace est comparé aux plans fixes d’origine, puis détaillé : rayonnages encastrés dans les murs, papiers posés à la main plutôt qu’en grille, panneaux lisibles.

**Destruction.** Trois cas sont construits et testés dans le moteur :
- **Les armoires d’armes** du sas : une balle traverse la vitre en acrylique, perd une partie de son énergie et atteint l’arme derrière ; la serrure et chaque charnière peuvent être touchées séparément ; une porte que plus rien ne retient tombe et reste au sol ; un support brisé fait tomber le peigne et les armes basculent.
- **Un mur carrelé** : le carreau, son lit de mortier et le béton derrière sont des couches distinctes ; un carreau touché encore et encore éclate, le béton ne prend qu’un cratère.
- **L’extincteur** : un impact sur la vanne libère le jet par le haut ; un impact haut sur le corps l’arrache de son support, et le jet comme les marques le suivent dans sa chute ; des impacts groupés font éclater la coque, des impacts dispersés jamais.

Trous, marques, portes et morceaux tombés se sauvegardent et se restaurent à l’identique, et le résultat d’une suite de tirs est le même à différentes cadences d’image.

**Akropolis.** Toute la zone a été cartographiée et reconstruite en structure praticable : dix-sept zones, vingt portes fonctionnelles, plus de deux cents plans fixes d’origine. La première passe de décor couvre la promenade en plein air et son escalator sous verrière, la chapelle et le belvédère. Les planches publiées montrent cette **passe de structure** : des volumes sans textures et un éclairage provisoire sur les cadrages d’origine.

## Le laboratoire Aya — point du 12 octobre 2026

Le projet reste une alpha. En parallèle de la reconstruction du M.I.S.T., un laboratoire Unreal séparé est désormais consacré au personnage jouable : sa façon de se déplacer, de se tenir, de viser et de manier son pistolet, et la cohérence de ses animations avec ce que fait le jeu. Travailler dans un projet séparé me permet de développer et d’éprouver ces systèmes avant de les intégrer au projet principal.

Trois chantiers, bien distincts :

1. **La reconstruction du M.I.S.T.**, présentée dans les images de cette vitrine.
2. **Les systèmes expérimentaux du laboratoire Aya**, décrits sur cette page.
3. **La recherche de l’apparence définitive d’Aya**, toujours en cours.

Le personnage animé dans le laboratoire est une base féminine provisoire, une ressource tierce adaptée aux essais. Ce n’est pas le modèle définitif d’Aya. Les derniers travaux du laboratoire ne sont pas encore intégrés au projet principal, et cette mise à jour est uniquement textuelle : les nouvelles images du personnage ne sont pas encore prêtes à être montrées.

### Déplacements et présence

Le laboratoire couvre les bases : repos, marche, course, déplacements en visée et pas latéraux. Ces animations sont conçues pour le mannequin standard du moteur et transférées sur la base féminine, qui bouge ainsi avec elles.

Ce transfert a apporté un défaut : le haut de son dos était courbé d’environ 17° vers l’avant et son cou d’environ 25°, si bien qu’elle paraissait voûtée. Une correction constante la redresse désormais. Son inclinaison générale est passée d’environ 10° à moins de 3°, comme au repos, et son regard est à l’horizontale.

Quand elle reste immobile sans viser, elle n’est plus figée. Elle respire (environ 14 respirations par minute), se balance légèrement sur deux rythmes qui ne se répètent jamais tout à fait, et porte son regard dans une nouvelle direction toutes les quelques secondes. Cette couche apparaît en douceur quand elle s’arrête et s’efface dès qu’elle bouge ou vise ; sa pose de visée apparaît et disparaît de la même façon.

Le but : un personnage présent, même quand personne ne touche aux commandes. Ces éléments fonctionnent à différents niveaux dans le laboratoire et restent en cours de finition.

### Visée et tenue du pistolet

- **Dans sa propre main.** Le pistolet était accroché à la main de la source d’animation invisible : il flottait à côté de la sienne. Il est maintenant attaché à sa propre main.
- **Bras et poignets.** Un bras qui se vrillait et un poignet trop plié sont corrigés : le canon est dans l’axe de l’avant-bras, et la crosse repose dans le creux entre le pouce et l’index.
- **Sa propre pose de visée.** Buste droit, tête droite, bras presque tendus, pistolet devant l’œil droit. Avant, elle copiait la pose compacte du mannequin, qui ramenait le pistolet contre son visage.
- **Doigts et main de soutien.** Le pouce droit reste hors du trajet de la glissière. L’index repose sur la détente pendant la visée, et le long de la carcasse quand elle manipule l’arme. La main gauche adopte la prise décrite par les manuels de tir : talon de la main sur la plaquette de la crosse, doigts enroulés sous le pontet, pouces vers l’avant.
- **Continuité entre les poses.** Chaque position de main est calculée selon la direction d’où arrive l’avant-bras pendant le geste, ce qui évite les retournements brusques du poignet.
- **Un cadrage plus rapproché pendant la visée** est à l’essai, pour mieux lire le pistolet et les mains. Ses réglages sont provisoires : c’est un essai du laboratoire, pas le système de caméra du jeu.

Les poses des mains sont calculées sur la forme réelle du pistolet, pour que les doigts l’entourent sans le traverser, puis jugées sur des images en jeu plutôt que sur les seuls chiffres. Le but : une prise qui ressemble à un geste entraîné, pas à une pose. La visée vers le haut et vers le bas n’est pas encore réalisée.

### Rechargements et munitions

Appuyer sur Recharger ne produit pas toujours le même geste ; tout dépend de ce qui reste dans l’arme :

- **Arme vide : rechargement complet.** La glissière reste bloquée en arrière après le dernier tir, le chargeur vide tombe au sol comme un objet physique, un nouveau chargeur sort de la poche, puis la glissière relâchée chambre une cartouche.
- **Chargeur entamé : rechargement tactique.** Aya conserve l’ancien chargeur : les cartouches qui y restent ne sont pas perdues.
- **Chargeur plein : courte inspection.** Les munitions ne changent pas.

Le rechargement à vide a été retravaillé et vérifié en jeu sur la base féminine actuelle. Le rechargement tactique et l’inspection courte ont été prototypés sur le premier mannequin d’essai ; ils doivent encore être adaptés et affinés sur cette base.

L’essentiel du travail consiste à garder d’accord les mains, le chargeur, la glissière et le compte des munitions. L’état de l’arme ne change qu’à des moments précis du geste (chargeur retiré, chargeur inséré, arme prête), chacun appliqué une seule fois et dans l’ordre ; un signal de l’animation répété ou en retard ne change rien. Si un rechargement est interrompu avant le retrait du chargeur, il est simplement annulé. S’il est interrompu en cours de route, l’arme reste ouverte et ne peut pas tirer jusqu’à la reprise du rechargement à la bonne étape. L’objectif : aucune cartouche perdue ni dupliquée, et aucun chargeur affiché au mauvais endroit.

### Réactions au tir

- **Glissière.** Elle recule et revient à chaque tir, ce qui laisse sortir la douille ; elle reste bloquée en arrière quand l’arme est vide, et le rechargement la relâche. Elle se déplace désormais dans l’axe du canon.
- **Recul.** Pendant la visée, les bras se relèvent puis reviennent avec un mouvement bref, comme un ressort. Les valeurs viennent d’une estimation physique, pas de mesures.
- **Flash de bouche.** Un éclair bref accompagné d’une lumière ; sa forme, sa taille et son intensité varient d’un tir à l’autre.
- **Douilles.** Chacune sort de la fenêtre d’éjection avec une vitesse et une rotation légèrement différentes : elles ne prennent pas la même trajectoire et ne tombent pas au même endroit. Elles rebondissent, roulent puis s’immobilisent. Au-delà d’un certain nombre au sol, les plus anciennes disparaissent.
- **Chargeur vide.** Il tombe comme un objet physique pendant le rechargement à vide.

Ensemble, ces effets donnent du poids à chaque tir et font du pistolet un mécanisme qui fonctionne. Ils restent en développement. Le laboratoire n’a pas encore de sons de tir ni de douilles ; l’environnement du M.I.S.T. possède ses propres sons de réaction.

### Un easter egg expérimental

Demandez plusieurs fois à recharger alors que le chargeur est déjà plein, et Aya réagit. La caméra reste fixe, le reste du monde se met en pause, et elle s’avance vers la caméra, la regarde, tire légèrement la glissière pour montrer la cartouche dans la chambre, la relâche, puis revient exactement à sa place. Les munitions ne changent pas, et la scène peut être passée.

C’est une expérimentation, pas une cinématique définitive.

### L’apparence définitive d’Aya

La base animée dans le laboratoire n’est qu’une doublure. Pour Aya elle-même, j’ai exploré plusieurs pistes : préparer des modèles de base, les retoucher dans Blender, puis les conformer sur une base de personnage riggée. La ressemblance, le visage, les cheveux, les vêtements, le rig facial et certaines déformations restent à finaliser.

Ni la base provisoire ni la [fiche conceptuelle](CONCEPTS.fr.md#aya-brea--direction-visuelle) ne sont le modèle jouable définitif.

### Comment c’est vérifié

Deux types de contrôles, tenus séparés.

**Tests de logique**, sur les seules règles de munitions, sans animation. Résultats enregistrés dans le laboratoire, état au 12 octobre 2026 :

- le modèle de référence des règles passe 57 scénarios écrits ;
- sur 72 628 opérations aléatoires (30 séries), sa règle de comptage n’a jamais été prise en défaut : les cartouches dans l’arme, en main, en réserve et tirées font toujours le total de départ ;
- 33 erreurs injectées volontairement dans le modèle ont toutes été détectées par les tests ;
- la version moteur (Blueprint) donne les mêmes résultats que la référence sur les mêmes 57 scénarios et sur 14 601 opérations aléatoires comparées pas à pas.

**Vérifications en jeu**, en regardant le résultat dans le moteur :

- le rechargement à vide se déroule jusqu’au bout sur la base actuelle : ensuite, 20 cartouches dans l’arme, 40 en réserve et un chargeur au sol ;
- l’easter egg se joue du début à la fin, munitions inchangées, et Aya revient à son point de départ ;
- l’interruption et la reprise ont été essayées en jeu au début, sur le premier mannequin d’essai ;
- sur 20 tirs, les douilles se dispersent sur plus d’un mètre.

Les suites complètes de tests automatiques en jeu du laboratoire sont écrites mais n’ont pas encore été exécutées. Le laboratoire n’est donc pas entièrement validé.

### Ce qui reste à travailler

- l’adaptation du rechargement tactique et de l’inspection courte à la base actuelle ;
- les torsions et les contacts des mains et des avant-bras (l’avant-bras gauche se vrille fortement à l’insertion du chargeur) ;
- la vérification que les bras ne traversent jamais le buste ;
- la visée vers le haut et vers le bas ;
- les sons du pistolet et des douilles ;
- la validation du cadrage de la caméra ;
- l’apparence définitive d’Aya et son rig facial ;
- la validation complète en jeu ;
- l’intégration au projet principal, plus tard.
