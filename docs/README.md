# GithubProjects — tous mes dépôts GitHub, triés par l'audit

Regroupe les dépôts de `github.com/mazounirayan`, classés dans les catégories
définies par l'audit du profil (`audit-github/rapport-complet.html` dans `workProject`),
mises à jour au fil des renommages/fusions/suppressions faits depuis sur GitHub.

## 📑 Documents d'Audit, Monetisation & Intégration CV

Trois documents d'analyse approfondie ont été générés à la racine de ce dossier :
- 🏆 **[Classement & Roadmap des Projets](file:///c:/Users/mazou/Documents/GithubProjects/classement_et_roadmap.md)** : Tier list complète (Tier S à D), contexte technique et plan d'action stratégique sur 90 jours.
- 💼 **[Guide d'Intégration CV](file:///c:/Users/mazou/Documents/GithubProjects/cv_integration.md)** : Formulations STAR, puces prêtes à copier-coller et mots-clés ATS par profil de poste.
- 💰 **[Audit de Monetisation & Modèles Business](file:///c:/Users/mazou/Documents/GithubProjects/audit_monetisation_business.md)** : Grilles tarifaires, stratégies d'acquisition et projections financières pour les projets à fort potentiel.


## Dossiers (état vérifié le 2026-07-23, après ménage complet)

| Dossier | Sens | Contenu |
|---|---|---|
| `A_Vitrine` | Portfolio, prêts à montrer | MyAutoTrader_Project, KapsuleKorp, **family-ecosystem** (fusion androidFamilyAPI+FamilyApp), SMARTSHELF-AI, tassili_airlines, mazounirayan |
| `B_Solide` | Bons projets, un peu de polish à faire | React-RED, JarvisVibeCoding, TrainingGame, cleanCodeFront |
| `C_A_Nettoyer` | À documenter ou trancher | ML_5AL2, designPatternProjet, fill-rouge, **pa-ecaf** (fusion PA-Api+PA-React-Front), elMazUsine, fakeTiwtter, **bedremade** (nouveau, pas dans l'audit d'origine — TypeScript, privé) |
| `D_Archive` | Vieux exercices, faible valeur | projetJS, **workProject-legacy** (nouveau, pas dans l'audit d'origine — privé, HTML, pas de description) |
| `E_A_Supprimer` | Candidats suppression | app-ideas |
| `Forks_Equipe` | Forks de projets de camarades (pas notés A-E) | ProjetAnnuelle-2025, student-project-manager, PA-ECAF-2024, Agrofrugal, InitiationAuxTraitementsDistribues, BarkingGestionArchi |

**Supprimés pour de bon sur GitHub le 2026-07-22/23** (confirmé par l'utilisateur, dossiers locaux retirés) :
`androidFamilyAPI`, `FamilyApp` (→ family-ecosystem), `PA-Api`, `PA-React-Front` (→ pa-ecaf),
`PA-React-BackOffice`, `tassilli-clone`, `freetimeProject`, `backoffice`, `Grabslice`, `vitrine-react`,
`Clean_Code`, `FrontPA-projets`, `GaSBackend`, `NewPA`, `React_back`, `React_vitrine`, `fil-Rouge`.

5 autres dépôts mentionnés dans l'audit d'origine avaient déjà été supprimés avant (vérifié via l'API GitHub le 2026-07-21) :
`blockchainTd`, `hackathon`, `crypto`, `MyCryptoApp`, `AndroidStudioProjects`.

**Total actuel : 26 dépôts projet + `dev-workspace-sync`** (27 dépôts sur le compte GitHub).

## Basculer entre PC pro et PC perso sans galérer

Le problème : ces dépôts sont des repos GitHub séparés. Changer de PC veut dire
committer/pusher chacun à la main avant de partir, et puller chacun à la main en arrivant.

`dev-workspace-sync/` (dépôt GitHub privé séparé, cloné dans ce dossier) fournit deux
outils au choix — voir son README pour le détail :

```bash
# Option recommandée : mr (myrepos), depuis Git Bash
mr status
mr update
mr commit -m "wip: sync $(hostname) $(date +%F)"
```

```powershell
# Option alternative : script PowerShell maison, sans dependance
.\dev-workspace-sync\sync-all.ps1 status
.\dev-workspace-sync\sync-all.ps1 start
.\dev-workspace-sync\sync-all.ps1 save
```

Les deux font des commits avec un message générique (`wip: sync ...`). C'est fait pour
ne jamais perdre de travail en cours entre 2 machines, pas pour remplacer un historique
de commits propre sur les projets phares (`A_Vitrine`) — continuer à committer ces
derniers à la main quand un vrai jalon est atteint.

**Piège Windows connu** (voir aussi `dev-workspace-sync/README.md`) : certains repos
peuvent contenir des fichiers avec des noms invalides sous Windows (points ou espaces
en fin de nom). Git les affiche comme "supprimés" en local sans jamais pouvoir les
committer normalement — vérifié et neutralisé pour `SMARTSHELF-AI` via
`git update-index --skip-worktree`. Toujours vérifier `git status`/`mr status` avant un
`save`/`commit` sur un repo qui affiche ce genre d'état inattendu.

Pour récupérer les outils sur l'autre PC : `gh repo clone mazounirayan/dev-workspace-sync
GithubProjects\dev-workspace-sync`, copier `mrconfig.template` vers `GithubProjects/.mrconfig`,
puis reproduire la structure de dossiers ci-dessus (ou relancer le clonage complet via
`gh repo list mazounirayan`).
