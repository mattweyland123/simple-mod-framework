# Special File Types

## entity.json
A QuickEntity JSON. Will be automatically built and converted to TEMP/TBLU/TEMP.meta/TBLU.meta, then placed in the staging directory (which is eventually built into a patch).

## entity.patch.json
A QuickEntity patch JSON. If no mods have altered the same TEMP/TBLU, the latest version of it will be pulled from the game's files. Otherwise, the TEMP/TBLU are pulled from the previous mod's version.

The TEMP/TBLU are then converted to QN JSON, where the patch JSON is applied, and then converted back to TEMP/TBLU and placed in the staging directory.

## unlockables.json
A JSON with the following format:
```json
{
    "FIREARMS_HERO_PISTOL_KRUGERMEIER": {
        "Properties": {
            "RepositoryId": "c8a09c31-a53e-436f-8421-a4dc4115f633"
        }
    },
    "CUSTOM_ITEM_THAT_I_ADDED_WHICH_IS_ACTUALLY_THE_JAEGER_SNIPER": {
        "Id": "CUSTOM_ITEM_THAT_I_ADDED_WHICH_IS_ACTUALLY_THE_JAEGER_SNIPER",
        "Guid": "910asd56-0aea-4dac-93b7-a229faaoe24f",
        "Type": "weapon",
        "Subtype": "sniperrifle",
        "ImageId": "",
        "RMTPrice": 99,
        "GamePrice": 99,
        "IsPurchasable": false,
        "IsPublished": true,
        "IsDroppable": false,
        "Capabilities": [],
        "Qualities": {},
        "Properties": {
            "Gameplay": {
                "range": 1.0,
                "damage": 1.0,
                "clipsize": 0.2,
                "rateoffire": 0.3
            },
            "Name": "UI_FIREARMS_HERO_SNIPER_HEAVY_BASE_NAME",
            "Description": "UI_FIREARMS_HERO_SNIPER_HEAVY_BASE_DESC",
            "Quality": 4,
            "Rarity": "common",
            "LoadoutSlot": "carriedweapon",
            "RepositoryId": "370580fc-7fcf-47f8-b994-cebd279f69f9",
            "UnlockOrder": 5
        },
        "Rarity": "common"
    }
}
```

The unlockables mentioned in the file are automatically added/edited in the unlockables ORES. Partial edits of existing items are supported (properties will be traversed and assigned).

## repository.json
A JSON with the following format:
```json
{
    "7a714602-2103-4271-9766-233b9e2154db": {
        "Image": "images/customImages/formerPrimeMinisterOfAustralia.jpg",
        "Name": "Kevin Rudd"
    },
    "7a62219e-008a-4a0a-b233-768d39287842": {
        "ID_": "7a62219e-008a-4a0a-b233-768d39287842",
        "Image": "images/actors/actor_a166a37e-a3f8-42d2-99d6-e0dd2cf5c090_1_0_0.jpg",
        "Name": "Thisguy's Adeadman",
        "Outfit": "a166a37e-a3f8-42d2-99d6-e0dd2cf5c090",
        "OutfitVariationIndex": 1.0,
        "CharacterSetIndex": 0.0,
        "Description": "Unknown",
        "Description_LOC": "actor_description",
        "Tile": "images/actors/default_target.png"
    }
}
```

The repository items mentioned in the file are automatically added/edited in the repository file. Partial edits of existing items are supported (properties will be traversed and assigned).

## contract.json
A contract JSON. The contract inside is automatically given a custom hash (determined by "smfcontract" + the contract's UUID), added to the contracts ORES and placed in the staging directory. If you want to edit an existing contract, instead use a raw file.