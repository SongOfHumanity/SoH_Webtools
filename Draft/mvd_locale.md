# MVD: LOCALE (DISTRICT / PATH / FEATURE / COMPONENT) v0.7
-------

## District Block
*Root_index*

A **District** is the Societal Root Container for indexing Features, Characters, and Inventories using MVD. The District ID ensures IDs of contained elements remain unique.

```
{DistrictID} — **{DistrictName}** · {FunctionTitle}
	**Elevation**: {ElevationTier} (High | Mid | Low)
	**Terrain**: {TerrainNotes}
	**Description**: {DistrictDescription}
	
	🔗_index: {Path List}
	
	{FeatureLetter}_index: {Feature List}
```

#### **Field Explanation**

| **Field** | **Purpose** | **Example/Notes** |
|-----------|-------------|-------------------|
| **Header** | `{DistrictID} — **{DistrictName}** · {FunctionTitle}` | Quick-scan identifier (e.g., `③ — **Town Square** · Shopping District`) |
| **Elevation** | Terrain tier (High, Mid, Low) | *Mid (8-12m above river)* |
| **Terrain** | Physical characteristics | *Gently sloping toward the Quay (⑦), cobbled plaza with drainage gutters* |
| **Description** | 1-2 sentence cultural/functional summary | *The civic and commercial heart of Silverwall, centered on the Root & Ring fountain. Shops line the square, their signs bright and inviting.* |
| **🔗_index** | Direct Paths to adjacent Districts | List of connected Districts with optional Path type (e.g., *Road*, *Bridge*, *Ferry*) |
| **{FeatureLetter}_index** | List of Features in the District | *③ⓐ Root & Ring, ③ⓑ Crystal Carafe, ③ⓒ Bee & Basket...* |

---
### Path Block
*🔗_index*

**Paths** are used to connect between Areas. Initial Development. 

```
🔗(1-9); {ConnectedDistrictID} · {PathType} ({PathName}) · {CompassPoint}
```

##### **Block Explanation**

| **Field** | **Purpose** | **Example/Notes** |
|-----------|-------------|-------------------|
| **Index** | `🔗(1-9)` | Local token for the Path (max 9 connections per District) |
| **ConnectedDistrictID** | District at the other end of the Path | *①*, *②*, *④*, *⑤*, *⑦* |
| **PathType** | Type of connection | *Road*, *Bridge*, *Ferry*, *Footpath*, *Gate*, *Stairs* |
| **PathName** | Optional name for the Path | *Main Street*, *Rivergate Bridge*, *Quay Ferry*, *Market Lane* |
| **CompassPoint** | Direction of the connected District | *N*, *E*, *S*, *NE*, *SW* |

-------

## **Featured Entry**
*Index Container: "🔩,🔮, 👤, 🐾, 📦, 🛎️, 🐓;"*
**Features** are Containers for a variety of elements, and provide details related to the physical Area of any particular landmark. 1BV is a place for about four people to work or live.

---
## `{FeatureLetter}`– Feature Block
*`{DistrictID}`_index* (*implied*)
A specific location or landmark within a District.

```
{DistrictID}{FeatureLetter} – **{FeatureName}** · {FunctionTitle}
	{LocalName} · {BV}BV{OPT: (Tall)|(Spread)} 
	**Area**: {FeatureArea}
	**Function**: {Function}
	**Sign**: {Sign}
	**Owner**: {Owner}
	**Sensory**: {SensoryHook}
	**Limitation**: {Limitation}
	**Construction**: {ConstructionStyle}
	{OPT_Indices}:
	🔩_index: {Feature:Component BlockList, max 9}
	🔮_index: {Feature:Arcana BlockList, max 9}
	👤_index: {Character:Persona BlockList, max 9}
	🐾_index: {Characer:Companion BlockList, max 9}
	📦_index: {Inventory:Item BlockList, max 9}
	🛎️_index: {Inventory:Service BlockList, max 9}
	🐓_index: {Inventory:Fauna BlockList, max 9}
```

#### **Field Explanation**
| **Field** | **Purpose and Rationale** | **Example/Notes** |
|-----------|---------------------------|-------------------|
| **Header** | `{DistrictID}{FeatureLetter} – **{Name}** · {FunctionTitle}` | Quick-scan identifier (e.g., `③ⓑ – **Crystal Carafe** · Apothecary`). |
| **FeatureName** | Full official name | *The Kettled Boar*, *Hammer & Helm*, **Root & Ring* |
| **FunctionTitle** |Stated Funtionality | *Inn & Tavern*, *Blacksmith*, *Fountain & Outdoor Market* |
| **LocalName** | Colloquial Name that may be used in-Setting | 'The Boar', 'Bigsmith' , 'The Fountain' |
| **BV** | Building Value (1-12) + optional modifier | *3*, *6 (Tall)*, *5 (Spread)* |
| **FeatureArea** | Physical location and context within the District | *"Northeast corner, near the Silver Wall"* / *"Central plaza, adjacent to the fountain"* / *"Low-lying, prone to spring flooding"* / *Optional: Locale Grid coordinates (e.g., [12,08])* |
| **Function** | Primary purpose or services, comma separated list | *Inn, tavern, kitchen, storage* or *Blacksmith, weaponsmith, armorer* |
| **Sign** | Physical marker or external indicator | *"A boar, tipsy and teetering over a bubbling pot"* / *"A bundle of herbs tied with red twine"* / *"No sign—just the red door everyone knows"* |
| **Owner** | Who owns/controls it | Person (e.g., *Garan Proudside*), Civic (*Mayor's Office*), Family (*The Loam Family*), Communal (*Town Council*) |
| **SensoryHook** | The *defining* sensory detail | *"Tanned hide, beeswax, the faint tang of iron"* / *"Bread crust and wood smoke"* |
| **Limitation** | Narrative hook—what makes it tricky? | *"Harven's arthritis slows fine work"* / *"The well runs shallow in summer"* / *"Rumors keep customers wary"* |
| **ConstructionStyle** | Material palette (from predefined list) | *Timber & Daub*, *Stone & Slate*, *Plank & Pitch*, etc. |
| **Indices** | Optional—only include if populated | 🔩_index, 🔮_index, 👤_index, 🐾_index, 📦_index, 🛎️_index, 🐓_index |

-----

### OPTION: **ConstructionStyle**

```
{ConstructionStyle}=[OPTION: 1 | 2 | 3 | 4 | 5 | 6 | 7 | hybrid]

1. **Timber & Daub** — Wood frame, wattle-and-daub walls, thatch or shake roof. Common, warm, prone to settling.
2. **Stone & Slate** — Cut stone or mortared fieldstone, slate roof. Upscale, durable, cold unless heated.
3. **Plank & Pitch** — Heavy timber planks, tar-sealed seams, simple roof. Functional, used for stables and barns.
4. **Brick & Tile** — Fired brick, clay tile roof. Rare, requires a kiln, long-lasting. Guild buildings, wealthy homes.
5. **Patchwork** — Salvaged materials, uneven construction, visible repairs. Functional but fragile.
6. **Canvas & Frame** — Tent-like structures, wood frame with oiled canvas. Market stalls, seasonal housing.
7. **Cob & Thatch** — Mud-and-straw walls, thick and insulating, thatched roof. Farmsteads, outlying homes.
```

**Usage:** Features can use one style, or a **hybrid** (e.g., *"Timber & Daub with Stone foundation"*).

-----

#### 🔩– Component Block
*`{DistrictID}{Feature Letter}`🔩_index*

Components are used to break down **Complex Features** (5+ BV) into manageable sub-units. Each Component represents a distinct functional or spatial division within the Feature—e.g., *Main Hall*, *Kitchen*, *Storage*, *Coop*.

```
		🔩(1-9); **{ComponentName}** · {ComponentFunction}
			- {BV}BV{OPT: (Tall)|(Spread)} · {ConstructionStyle}
			- {Description[Brief]}
```

##### **Block Explanation**

| **Field** | **Purpose** | **Example/Notes** |
|-----------|-------------|-------------------|
| **Index** | `🔩(1-9)` | Local token for the Component within the Feature (e.g., `②ⓐ🔩1`). |
| **ComponentName** | Name of the sub-unit | *Main Hall*, *Kitchen*, *Storage Shed*, *Guest Rooms*, *Coop* |
| **ComponentFunction** | Primary purpose of this Component | *Dining and socializing*, *Food preparation*, *Dry goods storage*, *Lodging*, *Chicken housing* |
| **BV** | Building Value for this Component | *2*, *1*, *1 (Spread)* |
| **ConstructionStyle** | Material palette (from predefined list) | *Timber & Daub*, *Plank & Pitch*, *Stone foundation* |
| **Description** | Brief flavor text (1-2 sentences) | *"The main hall smells of stew and wood smoke, with long tables scarred by years of use."* |

---
### **Notes**
- Paths are **bidirectional by default** (if ③ connects to ①, then ① connects to ③).
- **Special Paths** (bridges, ferries, gates) should be noted in the `{PathType}` field.
- **Path Names** are optional but helpful for narrative purposes (*"Meet me at the Rivergate Bridge"*).
- Components are **optional**—only use them for Features with 5+ BV that need internal breakdown.
- Each Component can have its own **Inventory indices** (📦, 🛎️, 🐓) if needed, but this is rare. Usually, Inventory stays at the Feature level.
- Components inherit the Feature's **{Owner}** unless specified otherwise (e.g., a tenant in one wing of a building).

-------
##### **Credit**: Team Silverwall