# ACR Migrate

Un ensemble d'outils qui convertissent les fichiers de définition de rapport ActiveReports (RPX) et Microsoft RDL/RDLC vers le format de définition de rapport [ACR (Across Report Renderer)](https://acrossreport.com) (`.acr`).

Deux convertisseurs sont fournis sous forme de binaires Windows.

| Outil | Convertit depuis | Précision |
|-------|-------------------|-----------|
| `rpx2json.exe` | ActiveReports `.rpx` | Haute fidélité (coordonnées absolues — peu ou pas d'ajustement de position nécessaire) |
| `rdl2json.exe` | Microsoft RDL / RDLC `.rdlc` | Meilleur effort (les éléments de type tableau utilisent des coordonnées estimées ; une vérification de la mise en page dans ACR Designer est attendue) |

Les deux outils sont gratuits, y compris pour la redistribution. Le code source n'est pas publié, mais l'exécution et la redistribution ne sont soumises à aucune restriction.

---

## Plateforme prise en charge

Windows uniquement (x64). ActiveReports Designer et les concepteurs RDL n'existant eux-mêmes que sous Windows, aucune prise en charge d'autres plateformes n'est prévue pour l'instant.

---

## Téléchargement

Téléchargez la dernière archive zip depuis les [Releases](../../releases). Aucune installation n'est nécessaire — il suffit de l'extraire et de l'exécuter.

---

## Utilisation

### rpx2json.exe (depuis ActiveReports RPX)

```
rpx2json.exe fichier.rpx
```

Crée un fichier `.acr` de même nom, dans le même dossier.

```
rpx2json.exe Report.rpx
# → Report.acr est créé
```

Les sections RPX utilisant des coordonnées absolues, peu ou pas d'ajustement de position n'est nécessaire après la conversion.

### rdl2json.exe (depuis Microsoft RDL/RDLC)

```
rdl2json.exe fichier.rdlc
```

Crée un fichier `.acr` de même nom, dans le même dossier.

```
rdl2json.exe report.rdlc
# → report.acr est créé
```

RDL résolvant la mise en page des tableaux (Tablix) au moment du rendu, le fichier converti indique des coordonnées estimées pour ces éléments. **Ouvrez le résultat dans ACR Designer pour vérifier et ajuster la mise en page.** Les sous-rapports (Subreport) ne sont pas pris en charge actuellement.

---

## Ouvrir le fichier converti

Le fichier `.acr` obtenu peut être ouvert dans [ACR Designer](https://acrossreport.com) pour l'impression, l'export PDF et l'ajustement de la mise en page. Si vous ne disposez pas d'ACR Designer, téléchargez-le depuis [acrossreport.com](https://acrossreport.com).

---

## Support

Ces outils sont fournis gratuitement, sans garantie ni obligation de support. Si vous avez besoin d'aide pour la migration (ajustement de la mise en page après conversion, migration en masse de nombreux fichiers, etc.), un support payant est disponible sur demande. Contact : across.support@gmail.com

---

## Licence

Copyright (C) 2026 Across Systems Corporation.

Exécution et redistribution libres. Décompilation et modification interdites. Voir le fichier LICENSE.txt fourni pour plus de détails.
