# **Incipium's Anno 1800 Modding Reference**

This is a guide to my mod, [Incipium's Tweaks and Enhancements](https://www.nexusmods.com/anno1800/mods/15). It is also a reference for GUIDs to help other modders or players.

## How To

In each folder you will find an assets.xml way at the bottom of the folder hierarchy.
Open it up in a text editor and you can modify the values. Some are self explanatory while others are a bit unclear.

# Increased Productivity

## EffectTargets

By default this mod affects all production buildings + all production buildings in the Arctic.

This is what is listed under `EffectTargets`.

To change what gets affected you must modify the <Item> values. 

*If you want to change it so it only affects **Farms** and **Mines** then you'll have to change it to the following:*
```
<EffectTargets>
  <Item>
    <GUID>190786</GUID>
  </Item>
  <Item>
    <GUID>190011</GUID>
  </Item>
</EffectTargets>
```
## FactoryUpgrade

By default the mod increases the productivity of the production buildings by 100%.

To change the value that it increases you can change the `Value` under `ProductivityUpgrade`

*If you want a **50%** increase instead of **100%** then change it to the following:*
```
<FactoryUpgrade>
  <ProductivityUpgrade>
    <Value>50</Value>
    <Percental>1</Percental>
  </ProductivityUpgrade>
</FactoryUpgrade>
```
# Variable Fields & Areas

## EffectTargets

Same concept as explained in Increased Productivity.

## FactoryUpgrade

By default the mod makes any production building that requires free space around it e.g. Lumberjack's Hut work with no productivity loss when there are overlapping buildings.

*This value will probably not need to be changed.*
```
<FactoryUpgrade>
  <NeededAreaPercentUpgrade>
    <Value>-100</Value>
  </NeededAreaPercentUpgrade>
</FactoryUpgrade>
```
## ModuleOwnerUpgrade

By default the mod makes any production building that requires modules e.g. Crop and Animal Farms etc. require 100% less modules.

What's important to note is that when you use an item that increase the amount of modules needed or if you use tractors, then the needed modules will increase again.

*To prevent this, change the `ModuleLimitPercent` to a bigger value.*
```
<ModuleOwnerUpgrade>
  <ModuleLimitPercent>-400</ModuleLimitPercent>
</ModuleOwnerUpgrade>
```
# Better Services

## EffectTargets

Same concept as explained in Increased Productivity, but these EffectTargets are for public buildings.

## BuildingUpgrade

These values are mostly self explanatory. 

*To increase the range that public buildings reach, increase the values.*
```
<BuildingUpgrade>
  <PublicServiceFullSatisfactionDistance>
    <Value>200</Value>
    <Percental>1</Percental>
  </PublicServiceFullSatisfactionDistance>
  <PublicServiceNoSatisfactionDistance>
    <Value>200</Value>
    <Percental>1</Percental>
  </PublicServiceNoSatisfactionDistance>
```
The emergency buildings are also modified with resolver units.

`ResolverUnitCountUpgrade` determines the amount of firemen, policemen etc.

`ResolverUnitDecreaseUpgrade` sounds confusing, but it actually increase the speed at which the firemen, policemen etc. resolve an incident.

`ResolverUnitMovementSpeedUpgrade` increases their movement speed.
```
  <ResolverUnitCountUpgrade>
    <Value>1</Value>
  </ResolverUnitCountUpgrade>
  <ResolverUnitDecreaseUpgrade>
    <Value>100</Value>
    <Percental>1</Percental>
  </ResolverUnitDecreaseUpgrade>
  <ResolverUnitMovementSpeedUpgrade>
    <Value>100</Value>
    <Percental>1</Percental>
  </ResolverUnitMovementSpeedUpgrade>
</BuildingUpgrade>
```
# Power Plants

## EffectTargets

Same concept as explained in Increased Productivity, but these EffectTargets are for power plants.

## PowerplantUpgrade

`IndustrializationRangeUpgrade` increases the range that the power plant reaches.
```
<PowerplantUpgrade>
  <IndustrializationRangeUpgrade>
    <Value>100</Value>
  </IndustrializationRangeUpgrade>
</PowerplantUpgrade>
```
## IndustrializableUpgrade

`ElectricityBoostUpgrade` increases the productivity boost you get from having electricity.
```
<IndustrializableUpgrade>
  <ElectricityBoostUpgrade>
    <Value>100</Value>
    <Percental>1</Percental>
  </ElectricityBoostUpgrade>
</IndustrializableUpgrade>
```
# Faster Ships

## EffectTargets

Same concept as explained in Increased Productivity, but these EffectTargets are for ships.

`ForwardSpeedUpgrade` increases the movement speed of ships.
```
<VehicleUpgrade>
  <ForwardSpeedUpgrade>
    <Value>100</Value>
    <Percental>1</Percental>
  </ForwardSpeedUpgrade>
</VehicleUpgrade>
```
`LoadingSpeedUpgrade` increases the speed that ships load/unload at harbours. 
```
<TradeShipUpgrade>
  <LoadingSpeedUpgrade>
    <Value>100</Value>
    <Percental>1</Percental>
  </LoadingSpeedUpgrade>
</TradeShipUpgrade>
```
# Increased Population

## EffectTargets

Same concept as explained in Increased Productivity, but these EffectTargets are for residences.

## PopulationUpgrade

`ResidentsUpgrade` is a percentage increase of the max amount of residents.

  **VERY IMPORTANT**
    
Under `InputBenefitModifier` are a lot of items. Under each `Product` is `AdditionalSupply`.
    
You **must** change the ``ResidentsUpgrade`` value and the `AdditionalSupply` value **proportionally**. 
    
If the value is **50**, then ALL of the `AdditionalSupply` values **MUST** be **5**. 
      
*or*
    
If the value is **400**, then ALL of the `AdditionalSupply` values **MUST** be **40**.

    These products are based on the item "Saint D'Artois, Vision of the Valley" and 2 were added for Enbesa to work.

*DO NOT USE INCIPIUM'S INCREASED POPULATION WITH ANY OTHER POPULATION MOD OR MY PREVIOUS VERSION'S INCREASED POPULATION!*

My population mod is the only one that works with Town Hall items. The previous version of my mod, and other population mods don't work when you use Town Hall items that further increase the max residents.