# Besoins utilisateurs

1. Taux de consultation des patients dans un établissement X sur une période de temps Y
2. Taux de consultation des patients par rapport à un diagnostic X sur une période de temps Y
3. Taux global d'hospitalisation des patients dans une période donnée Y
4. Taux d'hospitalisation des patients par rapport à des diagnostics sur une période donnée
5. Taux d'hospitalisation par sexe, par âge
6. Taux de consultation par professionnel
7. Nombre de décès par localisation (région) et sur l'année 2019
8. Taux global de satisfaction par région sur l'année 2020

# Sources

## Décès (csv)

- nom
- prenom
- sexe
- date_naissance
- code_lieu_naissance
- lieu_naissance
- pays_naissance
- date_deces
- code_lieu_deces
- numero_acte_deces

## Activité professionnel de santé (csv)

- identifiant
- identifiant_organisation
- mode_exercice

## Etablissement de Santé (csv)

- adresse
- cedex
- code_commune
- code_postal
- commune
- complement_destinataire
- complement_point_geographique
- email
- enseigne_commerciale_site
- finess_etablissement_juridique
- finess_site
- identifiant_organisation
- indice_repetition_voie
- mention_distribution
- numero_voie
- pays
- raison_sociale_site
- siren_site
- siret_site
- telecopie
- telephone
- telephone_2
- type_voie
- voie

## Professionnel de santé (csv)

- identifiant
- civilite
- categorie_professionnelle
- nom
- prenom
- commune
- profession
- specialite
- type_identifiant

## Hospitalisation (csv)

- Num_Hospitalisation
- Id_patient
- identifiant_organisation
- Code_diagnostic
- Suite_diagnostic_consultation
- Date_Entree
- Jour_Hospitalisation

## Adher (BDD postgres)

- Id_patient int
- Id_mut int

## Consultation (BDD postgres)

- Num_consultation int
- Id_mut int
- Id_patient int
- Id_prof_sante int
- Code_diag string
- Motif string
- Date date
- Heure_debut heure
- Heure_fin heure

## Diagnostic (BDD postgres)

- Code_diag string
- Diagnostic string

## Laboratoire (BDD postgres)

- Id_labo int
- Laboratoire string
- Pays string

## Medicaments (BDD postgres)

- Code_CIS int
- Denomination string
- Forme_pharmaceutique string
- Voies_d_administration string
- Statut_administratif string
- Type_de_procedure string
- Etat_de_commercialisation string
- Date_AMM date
- StatutBdm string
- Num_autorisation_europeenne string
- Titulaire string
- Surveillance_renforcee bool

## Mutuelle (BDD postgres)

- Id_Mut int
- Nom string
- Adresse string(toujours null)

## Patient (BDD postgres)

- Id_patient int
- Nom string
- Prenom string
- Sexe string
- Adresse string
- Ville string
- Code_postal int
- Pays string
- EMail string
- Tel string
- Date date
- Age int
- Num_Secu int
- Groupe_sanguin string
- Poid float
- Taille int

## Prescription (BDD postgres)

- Num_consultation int
- Code_CIS int

## Professionnel_de_sante (BDD postgres)

- Identifiant int
- Civilite string
- Categorie_professionnelle string
- Nom string
- Prenom string
- Profession string
- Type_identifiant string
- Code_specialite string

## Salle (BDD postgres)

- Id_salle int
- Num_consultation int
- Code_bloc string
- Num_etage string
- Num_salle string

## Specialites (BDD postgres)

- Code_specialite string
- Fonction string
- Specialite string

## date (BDD postgres)

- date1 date
- date2 date