# Foncier Mayotte — Produit de référence

## Promesse
Simple pour le particulier. Exploitable par le professionnel.

## 6 parcours grand public
1. Trouver mon terrain
2. Retrouver un point / une borne
3. Comprendre un plan papier
4. Préparer un partage / une division
5. Vérifier la situation foncière
6. Transmettre mon projet à un professionnel

## Règles métier
- Ne jamais présenter un sommet cadastral comme une borne officielle.
- Ne jamais présenter un point GPS smartphone comme une limite juridique.
- Conserver les coordonnées source, le CRS, la date, la précision et la provenance.
- Toute détection automatique de CRS ou OCR doit être confirmée avant guidage/export.
- Séparer projet utilisateur et données validées par un professionnel.
- Afficher les surfaces de projet comme approximatives tant qu'elles ne sont pas validées.

## Formats professionnels cibles
PDF de synthèse, CSV de points, GeoJSON, KML. DXF dans une version ultérieure.

## Modèle de point
id, nom, type (projet/plan/gps/cadastral/pro), x_source, y_source, z_source,
crs_source, lon_wgs84, lat_wgs84, precision_m, date_observation, source,
photo, statut_validation, notes.

## Module Division
- sélectionner une parcelle
- ajouter des points sur carte ou au GPS
- dessiner des lignes/polygones de projet
- calculer surfaces/distances approximatives
- nommer les lots
- enregistrer photos/notes
- générer dossier « Projet non certifié »
- partager/exporter au géomètre

## Photo / plan
Capture -> correction perspective/contraste -> OCR tableau -> détection P/X/Y/Z ->
détection du référentiel -> validation utilisateur -> conversion -> carte -> guidage.

## Référentiels Mayotte à supporter
- WGS84 / GPS
- RGM23 / UTM 38S (EPSG:10674)
- RGM04 / UTM 38S (EPSG:4471)
- Cadastre 1997 / UTM 38S (EPSG:5879)
- altitude/hauteur conservée avec son type et sa source

## Architecture cible
Frontend PWA mobile-first; API serveur; PostgreSQL/PostGIS; stockage privé de documents;
moteur de transformation PROJ avec grilles IGN; OCR document; journal d'audit.
