# RDX Addoninventory
Addoninventory System for RedM Extended

## Requirements
- [RedM Extended](https://github.com/ThymonA/redm_extended)

## How to install
* Download the lastest version of RDX Addoninventory
* Copy and paste ```rdx_addoninventory``` folder to ```resources/rdx_addoninventory```
* Insert the .sql file into your database.
* Add ```ensure rdx_addoninventory``` to your ```server.cfg``` file
* Now you are ready!

## Usage
There are two types of inventories: shared and not shared.

- Shared inventories dont belong to a specific user. Example: foodstore items.
- None-shared inventories are created for every user in the server. They are created in db when player is loaded, Example: property items

### `addon_inventory` database information
An addon inventory must be configured in the database before using it. Don't forget to run a server restart afterwards (you can alternative restart the script and relog all clients)

| `name`   | `label` | `shared` |
| -------- | ------- | -------- |
| name of the inventory | label of the inventory (not used) | is the inventory shared with others? (boolean either `0` or `1`) |

```lua
TriggerEvent('rdx_addoninventory:getSharedInventory', 'society_police', function(inventory)
	inventory.addItem('bread', 1)
end)

TriggerEvent('rdx_addoninventory:getInventory', 'property', 'steam:0123456789', function(inventory)
	inventory.removeItem('water', 1)
end)

```
