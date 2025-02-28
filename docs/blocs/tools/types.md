---
sidebar_position: 1
title: Types
description: Comment définir le type d'outil nécessaire pour récolter un bloc ?
tags: [blocs, tools]
---

Depuis la 1.17, le type d'outil nécessaire pour récolter un bloc est défini par un tag attribué le contenant.

## Types d'outil de base

Si vous souhaitez que votre bloc soit récoltable à la main, il n'est pas nécessaire de l'ajouter dans un tag. Dans le cas contraire, assurez-vous d'ajouter votre bloc au(x) tag(s) our qu'ainsi votre bloc puisse se miner plus rapidement avec les outils associés (et si la [propriété](../properties) `requiresToolForDrops()` est définie, cela impliquera que les outils spécifiés seront les seuls pour récolter le butin du bloc) :
- Hache : `minecraft:mineable/axe`
- Pioche : `minecraft:mineable/pickaxe`
- Pelle : `minecraft:mineable/shovel`
- Houe : `minecraft:mineable/hoe`

## Types d'outil customs

Pour créer un type custom, il vous suffit de créer un tag (qui sera contenu dans le dossier `data/modid/tags/blocks`) ainsi que sa variable associée comme celle-ci :

```java
public static final Tag.Named<Block> MON_TOOL_TYPE = BlockTags.bind("modid:mon_tool_type");
```

Il vous suffira ensuite d'utiliser ce tag dans l'appel `super()` du constructeur de votre classe héritière de `DiggerItem`.