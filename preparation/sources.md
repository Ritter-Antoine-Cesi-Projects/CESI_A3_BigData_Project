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

| Champ                  | Type   |
| ---------------------- | ------ |
| nom                    | string |
| prenom                 | string |
| sexe                   | int    |
| date_naissance         | date   |
| code_lieu_naissance    | int    |
| lieu_naissance         | string |
| pays_naissance         | string |
| date_deces             | date   |
| code_lieu_deces        | int    |
| numero_acte_deces      | string |

## Activité professionnel de santé (csv)

| Champ                  | Type   |
| ---------------------- | ------ |
| identifiant            | int    |
| identifiant_organisation| string|
| mode_exercice          | string |

## Etablissement de Santé (csv)

| Champ                          | Type   |
| ------------------------------ | ------ |
| adresse                        | string |
| cedex                          | string |
| code_commune                   | int    |
| code_postal                    | int    |
| commune                        | string |
| complement_destinataire        | string |
| complement_point_geographique  | string |
| email                          | string |
| enseigne_commerciale_site      | string |
| finess_etablissement_juridique | int    |
| finess_site                    | int    |
| identifiant_organisation       | string |
| indice_repetition_voie         | string |
| mention_distribution           | string |
| numero_voie                    | int    |
| pays                           | string |
| raison_sociale_site            | string |
| siren_site                     | int    |
| siret_site                     | int    |
| telecopie                      | string |
| telephone                      | string |
| telephone_2                    | string |
| type_voie                      | string |
| voie                           | string |

## Professionnel de santé (csv)

| Champ                   | Type   |
| ----------------------- | ------ |
| identifiant             | int    |
| civilite                | string |
| categorie_professionnelle| string|
| nom                     | string |
| prenom                  | string |
| commune                 | string |
| profession              | string |
| specialite              | string |
| type_identifiant        | string |

## Hospitalisation (csv)

| Champ                       | Type   |
| --------------------------- | ------ |
| Num_Hospitalisation         | int    |
| Id_patient                  | int    |
| identifiant_organisation    | string |
| Code_diagnostic             | string |
| Suite_diagnostic_consultation| string|
| Date_Entree                 | date   |
| Jour_Hospitalisation        | int    |

## Adher (BDD postgres)

| Champ        | Type   |
| ------------ | ------ |
| Id_patient   | int    |
| Id_mut       | int    |

## Consultation (BDD postgres)

| Champ            | Type   |
| ---------------- | ------ |
| Num_consultation | int    |
| Id_mut           | int    |
| Id_patient       | int    |
| Id_prof_sante    | int    |
| Code_diag        | string |
| Motif            | string |
| Date             | date   |
| Heure_debut      | heure  |
| Heure_fin        | heure  |

## Diagnostic (BDD postgres)

| Champ     | Type   |
| --------- | ------ |
| Code_diag | string |
| Diagnostic| string |

## Laboratoire (BDD postgres)

| Champ        | Type   |
| ------------ | ------ |
| Id_labo      | int    |
| Laboratoire  | string |
| Pays         | string |

## Medicaments (BDD postgres)

| Champ                        | Type   |
| ---------------------------- | ------ |
| Code_CIS                     | int    |
| Denomination                 | string |
| Forme_pharmaceutique         | string |
| Voies_d_administration       | string |
| Statut_administratif         | string |
| Type_de_procedure            | string |
| Etat_de_commercialisation    | string |
| Date_AMM                     | date   |
| StatutBdm                    | string |
| Num_autorisation_europeenne  | string |
| Titulaire                    | string |
| Surveillance_renforcee       | bool   |

## Mutuelle (BDD postgres)

| Champ        | Type   |
| ------------ | ------ |
| Id_Mut       | int    |
| Nom          | string |
| Adresse      | string (toujours null) |

## Patient (BDD postgres)

| Champ          | Type   |
| -------------- | ------ |
| Id_patient     | int    |
| Nom            | string |
| Prenom         | string |
| Sexe           | string |
| Adresse        | string |
| Ville          | string |
| Code_postal    | int    |
| Pays           | string |
| EMail          | string |
| Tel            | string |
| Date           | date   |
| Age            | int    |
| Num_Secu       | int    |
| Groupe_sanguin | string |
| Poid           | float  |
| Taille         | int    |

## Prescription (BDD postgres)

| Champ            | Type   |
| ---------------- | ------ |
| Num_consultation | int    |
| Code_CIS         | int    |

## Professionnel_de_sante (BDD postgres)

| Champ                   | Type   |
| ----------------------- | ------ |
| Identifiant             | int    |
| Civilite                | string |
| Categorie_professionnelle| string|
| Nom                     | string |
| Prenom                  | string |
| Profession              | string |
| Type_identifiant        | string |
| Code_specialite         | string |

## Salle (BDD postgres)

| Champ            | Type   |
| ---------------- | ------ |
| Id_salle         | int    |
| Num_consultation | int    |
| Code_bloc        | string |
| Num_etage        | string |
| Num_salle        | string |

## Specialites (BDD postgres)

| Champ           | Type   |
| --------------- | ------ |
| Code_specialite | string |
| Fonction        | string |
| Specialite      | string |

## date (BDD postgres)

| Champ  | Type   |
| ------ | ------ |
| date1  | date   |
| date2  | date   |