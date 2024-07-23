# Guide d’annotation "anonymisation de documents cliniques"

## Introduction

Ce guide résume les lignes directrices sur lesquelles doivent se baser les annotateurs des documents.

L’objectif est d’avoir une annotation homogène pour différents annotateurs.

Comme défini par la CNIL et la RGPD, l’**anonymisation** est la suppression de toute donnée pouvant identifier directement ou indirectement un·e patient·e.

Le terme **identificateur direct** est utilisé pour désigner une information identifiant directement à un individu (Numéros de sécurité sociale, Noms, Prénoms, etc.).

Le terme **identificateur indirect** est utilisé pour désigner une information permettant l’identification d’un individu de manière indirecte (Dates de naissance, Médecins traitants, Adresses, etc.).

## Étiquettes

La manière dont chaque étiquette doit être utilisée est définie dans les sections ci-dessous.

Les balises \<NomEtiquette>\</NomEtiquette> sont utilisées pour illustrer les termes à étiquetter dans une phrase.

### Nom et Prénom

Les noms et prénoms sont des identifiants directs des personnes lié à un document.

Après quelques essais il a été décidé de regrouper les noms et prénoms dans une seule étiquette plutôt que d’en utiliser deux.

Cela nous permet d’avoir une étiquette englobant et généralisant le concept de nom/prénom.

Exemples:

Dr. Madelene Moreau -> Dr. \<NomPrenom>Madelene Moreau\</NomPrenom>

Mme Patry -> Mme \<NomPrenom>Patry\<NomPrenom>

Monsieur D. GIMBERT -> Monsieur \<NomPrenom>D. GIMBERT\<NomPrenom>

Prénom: Thomas, Nom: Marquis -> Prénom: \<NomPrenom>Thomas\</NomPrenom>, Nom: \<NomPrenom>Marquis\</NomPrenom>

### IPP

L’Identifiant Permanent du Patient (IPP) est, comme son nom l’indique, un identifiant direct d’un·e patient·e.

Il est composé d’un ensemble variant de numéro et est souvent précédé (ou suivi) de la mention "IPP".

Exemples:

IPP 8102840 -> IPP \<IPP>8102840\</IPP>

12301840 (IPP) -> \<IPP>12301840\</IPP> (IPP)

### Numéro de Sécurité Sociale

Comme décrit sur [ameli.fr](https://www.ameli.fr/isere/assure/droits-demarches/principes/numero-securite-sociale), le numéro de sécurité sociale est composé de 15 chiffres basés (entre autres) sur le sexe du/de la patient·e, ainsi que le mois, l'année et le département de naissance du de la patient·e.

Le numéro de sécurité sociale est donc un identificateur direct d'un·e patient·e.

Exemples:

N° Sécu: 1 85 05 78 006 084 36 -> N° Sécu: \<NoSecu>1 85 05 78 006 084 36\</NoSecu>

Immatriculation patient: 1850578006084 Clé 36 -> Immatriculation patient: \<NoSecu>1850578006084 Clé 36\</NoSecu>

### Numéro de dossier

Le numéro de dossier est l'identifiant d'un dossier médical d'un patient pour un Centre de Responsabilité précis. C'est un identificateur indirect permettant de remonter rapidement à l'identité d'un·e patient·e.

Exemple:

Dossier N° 464486432 -> Dossier N° \<NoDossier>464486432\</NoDossier>

dossier_id: 884018401 -> dossier_id \<NoDossier>884018401\</NoDossier>

N° Venue: 819014 -> N° Venue: \<NoDossier>819014\</NoDossier>

N° AZUR: HFME_81044_810 -> N° AZUR: \<NoDossier>HFME_81044_810\</NoDossier>

N° GEMA: 81084170 -> N° GEMA \<NoDossier>81084170\</NoDossier>

Fiche Id: ddoc_8199_8910 -> \<NoDossier>ddoc_8199_8910\</NoDossier>

Ref: DH/SA -> Ref: \</NoDossier>DH/SA\</NoDossier>

### Date

Les dates, telles que les dates de naissance ou les dates d'actes médicaux, sont des identificateur indirect d'un·e patient·e.

Celles-ci peuvent prendre plusieurs formes, toutes doivent être prise en compte.

Exemples:

consultation du 12/11/2013 -> consultation du \<Date>12/11/2013\</Date>

l'opération eu le lieu en Janvier 2020 -> l'opération eu lieu en \<Date>Janvier 2020\</Date>

Jeudi dernier -> \<Date>Jeudi\</Date> dernier

le 12/02/2019 11:03 -> le \<Date>12/02/2019\<Date> 11:03

### Adresse e-mail

Les adresses e-mail sont des identificateurs directs de médecins voir de patient·e·s, surtout si ceux-ci sont construit à partir d'un nom et d'un prénom.

Exemples:

mail: anne.honyme@chu-lyon.fr -> mail: \<EMail>anne.honyme@chu-lyon.fr\</EMail>

\<anne.honyme@chu-lyon.fr> -> \<EMail>\<anne.honyme@chu-lyon.fr>\</EMail>

mailto:anne.honyme@chu-lyon.fr -> \<EMail>mailto:anne.honyme@chu-lyon.fr\</EMail>

### Numéro de téléphone

Les numéro de téléphone sont des identificateurs indirects car les chiffres les composants peuvent permettre de remonter à un·e patient·e ou à une personne lié à ce·tte patient·e.

Exemples:

Tel: 0452359636 -> Tel: \<Telephone>0452359636\</Telephone>

à contacter au +33 934 693 684 -> à contacter au \<Telephone>+33 934 693 684\</Telephone>

dom:0289898273 -> dom:\<Telephone>0289898273\<Telephone>

### Code Postal

Les code postaux sont utilisés pour faciliter la distribution du courrier en identifiant une ville, un arrondissement ou un ensemble de village.

En France il est composé de 5 chiffres, les deux premiers identifiant un département et les trois autres une commune du département.

Il est généralement suivi part le nom de la commune en question.

Ceux-ci sont donc des identificateurs indirects d'un·e patient·e, en particulier si ils concernent l'adresse dudit/de la dite patient·e.

Exemples:

69000 Lyon -> \<CodePostal>69000\</CodePostal> Lyon

### Ville

La mention de villes ou communes dans un document clinique peuvent permettre de remonter à l'identité d'un·e patient·e. Ce sont donc des identificateurs indirects.

Exemples:

habitant à Grenoble -> habitant à \<Ville>Grenoble\</Ville>

69002 Lyon Cedex 2 -> 69002 \<Ville>Lyon Cedex 2\</Ville>

Lyon 9 -> \</Ville>Lyon 9\</Ville>

### Voie

La mention d'une voie (numéro et/ou nom rue, avenue, lieux-dits etc) peuvent permettre de remonter à l'identité d'un·e patient·e, en particulier si elles concernent l'adresse dudit/de la dite patient·e.

Celles sont donc des identificateurs indirects d'un·e patient·e.

Exemples:

résidant au 2 rue d'Enghien -> résidant au \<Voie>2 rue d'Enghien\</Voie>

localisé avenue lacassagne -> localisé \<Voie>avenue lacassagne\</Voie>

### Organisation

La mention d'une organisation (hôpitaux, entreprise, etc.) peut permettre de remonter à l'identifier d'un·e patient·e.

Ce sont donc des identificateurs indirects.

Exemples:

N° FINESS: 4654328 -> N° FINESS: \<Organisation>4654328\</Organisation>

N° FINESS HCL: 4654328 -> N° FINESS \<Organisation>HCL\</Organisation>: \<Organisation>4654328\</Organisation>

Hospices Civils de Lyon -> \<Organisation>Hospices Civils de Lyon\</Organisation>

Fédération de diabétologie et d'endocrinologie - HCL -> \<Organisation>Fédération de diabétologie et d'endocrinologie\</Organisation> - \<Organisation>HCL\</Organisation>

travail à la Mairie de Lyon -> travail à la \<Organisation>Mairie de Lyon\</Organisation>

Hopital Croix-Rousse Service de diabétologie et métabolisme -> \<Organisation>Hopital Croix-Rousse\</Organisation> \<Organisation>Service de diabétologie et métabolisme\</Organisation>

Unité kangourou, Unité 42 -> \<Organisation>Unité kangourou\</Organisation> \<Organisation>Unité 42\<Organisation>

### Localité

L'étiquette localité est à utiliser si, et seulement si, aucune des étiquettes précédentes ne permet d’étiqueter la mention d'un lieu/zone qui pourrait être considéré comme un identificateur direct ou indirect d'un·e patient·e.

Exemples:

Vient de la région Rhône-Alpes -> Vient de la région \<Localite>Rhône-Alpes\</Localite>

Réside en Allemagne -> Réside en \<Localite>Allemagne\</Localite>

### Site web

La mention d'un site web, ou d'une adresse url, peut constituer un identificateur indirect d'un·e patient·e, en particulier dans le cas des sites web personnel ou professionnel.

Exemples:

jameshfisher.com -> \<SiteWeb>jameshfisher.com\</SiteWeb>

https://fr.wikipedia.org/wiki/Separowo -> \<SiteWeb>https://fr.wikipedia.org/wiki/Separowo\</SiteWeb>