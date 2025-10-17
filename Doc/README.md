# Requirements

## 1. 初始化工作
### 1.1 启用UnLua作为脚本开发
### 1.2 配置GAS
### 1.3 先搭一个能用的3C
#### 1.3.1 基于Lyra的动画系统
#### 1.3.2 

## 2. 初步搭建物品系统、方块的破坏与建造
### 2.1 物品系统
```c++
class Block{
    Block(uint32 ItemID,FVector Position){
        m_ItemID = ItemID;
        cubemesh = spawnAt(Position);
        cubemesh.Material=ItemManager::get()
        ->getItem(m_ItemID)
        ->GetBlockMaterial();
    }
private:
    uint32 m_ItemID;
    CubeMesh* cubemesh;
}

class Entity{
private:
    Mesh* mesh;
    uint32 ItemID;

}


class ItemManager{

public:
    Item* getItem(uint32 ItemID){
        if(){

        }
        else{

        }
    };
    static ItemManager* get(){return s_Instance;}
private:
    static ItemManager* s_Instance;
    TMap<ItemID,Item*> Cache;
}

ItemManager* ItemManager::s_Instance = nullptr;
class Item {  
public:
    Item(uint32 _ItemID){ItemID=_ItemID;}  
    FString GetJsonPathByID(uint32 ItemID);
    
    virtual bool InitData()=0;
    //read value by json
    virtual Material* GetBlockMaterial()=0;
    virtual ItemType GetItemType();
private:
    uint32 ItemID=0;
    ItemType Itemtype=ItemType::None; 
    //block 
    Material* blockMaterial=nullptr;

    //entity
    Mesh* EntityMesh=nullptr;
}
```
ItemInstance
    ItemID
    StackCount

