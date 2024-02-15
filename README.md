# Markdown
# Heading 1
# Heading 2
# Heading 3
# Heading 4
# Heading 5
# Heading 6

## Lists

- item 1
- item 2
- item 3
* Dot
* More dots
1. Number 1
1. Number 2
1. Number 3

### Split for new list

1. New list
1. Second
1. Third

#### Codeblock

```
    void HandleUpgradeClick(Upgrade upgrade, GameObject upgradeObject)
    {
        if (upgrade.cost <= points && !upgrade.unlocked)
        {
            upgrade.unlocked = true;
            points -= upgrade.cost;
            var image = upgradeObject.GetComponent<Image>();
            image.color = green;
            totalScoreTMP.text = $"Total Score: {points}";
            GameObject blockBuildUI = Instantiate(blockUIPrefab, blockList.transform);
            image = blockBuildUI.GetComponent<Image>();
            image.color = upgrade.color;
            Button[] blockButtons = blockBuildUI.GetComponentsInChildren<Button>();
            TextMeshProUGUI[] blockTexts = blockBuildUI.GetComponentsInChildren<TextMeshProUGUI>();
            Button selectBlockButton = blockButtons[0];
            Button buyBlockButton = blockButtons[1];
            Block newBlock = new()
            {
                name = upgrade.name,
                prefab = upgrade.prefab,
                ownedText = blockTexts[0],
                costText = blockTexts[1],
                Cost = upgrade.cost,
                Owned = 0
            };

            if (newBlock.prefab != null)
            {
                blocks.TryAdd(newBlock.prefab.tag, newBlock);
            }
            else
            {
                Debug.LogError("Trying to unlock a block with NO PREFAB");
            }

            selectBlockButton.onClick.AddListener(() => HandleBlockSelect(newBlock));
            buyBlockButton.onClick.AddListener(() => HandleBlockBuy(newBlock));
        }
    }                            
```