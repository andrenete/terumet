# terumet
A mod for the open-source voxel game Minetest (https://www.minetest.net/)

Creates a new ore in the world which can be used to make useful alloys from many already available materials.

![Screenshot](https://github.com/Terumoc/terumet/blob/master/screenshot.png)

## Worldgen
The only new thing generated in the world is a new type of ore:
![Terumetal Ore]()
Which can be found in stone or desert stone:
![Terumetal Desert Ore]()

Like any other standard Minetest ore, mining it provides you with one or more raw lumps of ore, which can be cooked in a furnace to create ingots.

Do not make too many ingots from this new ore though because it is much better used as a flux for alloying than by itself; most tools made from raw Terumetal Ore will be very brittle, breaking quickly. In a pinch they *can* be useful since they are capable of digging very hard material quickly (and curiously, *ONLY* very hard material) but will only last a few blocks worth of digging.

## Alloy Smelter
The real use of Terumetal Ingots is creating an Alloy Smelter:
![Alloy Smelter Recipe]()
| Terumetal Ingot | Furnace | Terumetal Ingot |
|-----------------|--------------|-----------------|
| Empty Bucket | Copper Block | Empty Bucket |
| Terumetal Ingot | Furnace | Terumetal Ingot |

Place the smelter block down somewhere and you can then right-click it to access its interface, like a standard furnace:
![Alloy Smelter GUI]()

Before you begin using it, it's important to understand two things about the Alloy Smelter:
1. It requires heat to do anything.
2. The flux metal used to alloy with other materials is melted first and stored inside.

One useful thing to keep in mind is that unlike vanilla Minetest furnaces, the Terumetal Alloy Smelter *will* drop its contents when you break it. The only thing lost is any stored heat, which will be evaporated into the atmosphere. Also, thanks to some form of instant heat transfer techology, any molten flux metal left in the internal tank will be dropped as raw lumps of Terumetal, reusuable again later just at the cost of the heat and time to re-melt them.

### Heating the Alloy Smelter
The simplest way to get lots of heat quickly is with lava, and that is how the Smelter is heated.
When cold, the smelter displays its fuel slot in the upper-right corner, and is expecting a bucket of lava to be inserted into it.
![Alloy Smelter Fueling]()

Once inserted, the heat level will reflect the bucket-worth of lava now inside the machine by filling the heat bar, and your empty bucket will be refunded in the output section.

A single bucket of lava provides enough heat to operate for quite a while, but not forever. When the heat from the lava is fully dissipated, the fuel slot will reappear with the remaining cobblestone from the lava and any processing will stop until a new bucket of lava is inserted.
![Alloy Smelter Empty Heat]()

In quite a user-friendly manner, the smelter is amazingly heat efficient and none will be lost except by doing processing functions or by breaking the smelter itself.

### Flux Metal
The Terumetal Alloy Smelter is a specialized smelter only for making alloys from combining Terumetal and other materials, therefore it has an internal tank especially for molten Terumetal. This tank is shown on the left. It can be filled by inserting raw lumps of Terumetal into the input slot (*not* ingots) and then waiting a few seconds for each lump to melt. Naturally, this process requires heat and some will be spent by how much flux is melted.
![Alloy Smelter Melting Flux]()

When processing materials for alloying, a specific amount of molten flux will need to be in the tank to create the alloy. If not enough is present, it will indicate so and how much more is required until alloying can begin.

## Alloys
In total there are four alloys the smelter can create, all based on Terumetal and other materials available in the default Minetest game world. Each of them can be used to create hardened metal blocks and, of course, tools of considerable speed and durability. Each alloy has much greater tool performance than any of their constituent materials.

| Material | Flux/Ingot* | Time* | Alloy |  |
|----------------------------|-------------|---------|------------|----------------------|
| Copper Lump | 1 | 3 sec. | Terucopper | [Terucopper Ingot]() |
| Iron Lump | 2 | 4 sec. | Terusteel | [Terusteel Ingot]() |
| Gold Lump | 3 | 5 sec. | Terugold | [Terugold Ingot]() |
| Diamond and Obsidian Shard | 5 | 10 sec. | Coreglass | [Coreglass Ingot]() |
*note: Flux required and time shown are default.

See options.lua for ways to some ways to easily modify how the alloying process works.
