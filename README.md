
# Segmentation d'Images Médicales avec Swin U-Net et Augmentation par GAN

## Contexte

La segmentation précise des images médicales est cruciale pour améliorer les systèmes de soins de santé, notamment pour le diagnostic et la planification des traitements. Bien que les architectures en forme de "U" (telles que le U-Net) aient démontré leur efficacité, elles présentent des limites pour modéliser les dépendances globales entre pixels, essentielles pour les images médicales complexes. Notre approche combine les **transformers Swin U-Net** et **GANs** pour améliorer la segmentation des organes et tissus sur des images médicales, tout en générant des données synthétiques pour équilibrer notre dataset.

## Objectifs du Projet

- Utiliser le modèle **Swin U-Net** pour la segmentation d’images médicales, en tirant parti des transformers pour capturer des contextes globaux dans les images.
- Augmenter le dataset de manière contrôlée en utilisant des **GANs**, afin d'équilibrer la représentation des classes entre les images de poumons sains et malades.
- Réduire la charge de travail manuel des spécialistes médicaux et optimiser le temps d'analyse en fournissant des délimitations précises des régions d'intérêt.

## Données

Les données du projet incluent des images médicales de poumons :
- **Classes** : Images de poumons sains et de poumons malades.
- **Problème d’équilibrage** : Les données sont initialement déséquilibrées, avec plus d’images de poumons sains.
- **Augmentation des données** : Nous avons utilisé les **GANs** pour générer des images de poumons malades afin d’équilibrer le dataset.

## Approche et Méthodologie

### 1. **Prétraitement des Données**
   - Normalisation et mise à l'échelle des images pour assurer une entrée cohérente dans le modèle.
   - Augmentation de données via rotation, recadrage et transformations afin d’éviter le surapprentissage.

### 2. **Modèle Swin U-Net**
   - **Swin U-Net** : Nous utilisons les transformers Swin pour capter les dépendances globales tout en préservant la structure en U de U-Net pour une segmentation fine.
   - **Architecture** : L’architecture Swin U-Net permet d’utiliser une auto-attention spatiale, essentielle pour traiter les images complexes et capter les informations de manière hiérarchique.

### 3. **Augmentation par GAN**
   - **GANs (Generative Adversarial Networks)** : Nous avons employé des GANs pour générer des images médicales réalistes de poumons malades, augmentant ainsi la diversité de notre dataset.
   - **Utilisation spécifique** : Ces images synthétiques permettent d'équilibrer la distribution des classes pour un apprentissage plus stable et précis.

## Résultats

Les résultats montrent que l'utilisation de Swin U-Net améliore les performances de segmentation par rapport aux modèles traditionnels, en captant des informations globales et locales plus efficacement :
- **Précision de segmentation** : Précision élevée pour les zones d’intérêt ciblées.
- **Amélioration par rapport aux modèles standards** : Comparé aux modèles U-Net classiques, Swin U-Net présente une meilleure capacité à gérer les dépendances longues distances.
- **Impact de l'augmentation par GANs** : L’augmentation a permis d’atténuer le problème d’images déséquilibrées, améliorant la généralisation du modèle.

## Technologies et Outils

- **Langage** : Python
- **Bibliothèques** :
  - **PyTorch** : Pour implémenter le modèle Swin U-Net
  - **TensorFlow/Keras** : Utilisé pour le modèle GAN
  - **OpenCV** : Prétraitement et transformations d'images
- **Visualisation** : Matplotlib, Seaborn pour l’analyse et la visualisation des résultats

## Structure du Projet

├── A_Comprehensive_Approach.pdf     # Project documentation and report
├── Evaluation.ipynb                 # Notebook for evaluating model performance
├── GAN3D.ipynb                      # GAN-based data augmentation implementation in 3D
├── Preprocess.ipynb                 # Data preprocessing steps
├── Segmentation2D.ipynb             # 2D medical image segmentation using Swin U-Net
└── README.md                        # Project README file

## Installation et Exécution

1. Cloner ce repository :
   ```bash
   git clone https://github.com/votre-utilisateur/votre-repository.git
   ```

2. Installer les dépendances :
   ```bash
   pip install -r requirements.txt
   ```

3. Lancer un notebook Jupyter pour tester et entraîner le modèle :
   ```bash
   jupyter notebook
   ```

## Ressources

- **Documentation de PyTorch** : [https://pytorch.org/](https://pytorch.org/)
- **Article de référence sur Swin U-Net** : [https://arxiv.org/abs/2105.01002](https://arxiv.org/abs/2105.01002)
- **Documentation GAN** : [https://www.tensorflow.org/tutorials/generative](https://www.tensorflow.org/tutorials/generative)

## Auteurs

Projet réalisé par Ayyoub benrguig.

## NB
Voici le lien vers la data: https://drive.google.com/drive/folders/1bQ-j7mIh4oGpkddxwUbbN2-2vWOJit3b?usp=sharing
