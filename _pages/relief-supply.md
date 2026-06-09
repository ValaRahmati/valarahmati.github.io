---
layout: page
title: Relief Supply Network Planning - Data
permalink: /repositories/relief-supply/
nav: false
---

## Time-Phased Relief Supply Network Planning for Foreseen Disasters
**Authors:** Vala Rahmati and Halit Üster

---

### A. Computational Study Data

The link to download the instance data files used for the computational study is provided below:

<div class="text-center my-4">
    <a href="/assets/zip/Dataset.zip" class="btn btn-outline-primary" target="_blank" role="button">📦 Download Computational study Data Instances - Dataset.zip</a>
</div>

There are **24 Excel files** representing classes `C1 - C8` for 3 different networks `G1 – G3`. Within each file, there are 10 sheets representing instances that are randomly generated. The folder names follow a systematic naming convention to help users match configurations easily:

> **Folder Name Format:** `G[A]-C[B]-[C]-[D]-[E]-[F]-[G]-[H]`
> * **A:** Utilized graph index
> * **B:** Class Number
> * **C:** Number of DCs
> * **D:** Number of transfer nodes
> * **E:** Number of Shelters
> * **F:** Time periods
> * **G:** Number of relief items
> * **H:** Number of network arcs

* **Example:** `G2-C6-16-88-22-20-4-363` contains 10 instance sheets of class 6 applied on network 2 with 16 DCs, 88 transfer nodes, 22 shelters, 20 time periods, 4 relief items, and 363 arcs.
* Each instance sheet within a data file is named as **$I_i$** where $i = 1, \dots, 10$ (index number).

#### File Content Legend

| Symbol | Details |
| :--- | :--- |
| **DC List** | `[ID, X, Y, Item1_Capacity, Item2_Capacity, Item3_Capacity, Item4_Capacity, Fixed Cost]` <br> DC ID, (x, y) coordinates, capacity of items stored in that DC, and fixed cost for opening that DC. |
| **Transfer List** | `[ID, X, Y, Fixed Cost, Associated Preparation Cost]` <br> Transfer node ID, (x, y) coordinates, fixed cost of utilizing that transfer node, and associated preparation cost in the transfer node. |
| **Shelter List** | `[ID, X, Y, Capacity]` <br> Shelter ID, (x, y) coordinates, and the capacity of people hosted in that shelter. |
| **Arc List** | `[Origin ID, Destination ID, Fixed Cost, Variable Cost, Capacity, Distance]` <br> Arc's origin node ID, destination node ID, fixed cost of utilizing that arc, transportation cost of using that arc, arc capacity for relief items, and geodesic distance. |

---

### B. Case Study Data

The case study data parameters are completely available inside the `GIS-data` directory within `Dataset.zip`. All model parameters are structured into targeted Excel files labeled as follows:

#### 1. DC Data
All data structural attributes related to distribution centers are stored in this file.

| Header | Description |
| :--- | :--- |
| **ID** | Unique ID of the distribution center |
| **CNTY_NM** | County hosting the target DC |
| **Population** | Population metrics of the DC county |
| **X / Y** | Planar spatial coordinates |
| **Capacity_Item[1-4]** | Storage capacity threshold for relief items 1 through 4 |
| **Fixed_Cost** | Fixed economic investment required to open the DC |

#### 2. Transfer Data
All structural attributes related to network transfer nodes are stored in this file.

| Header | Description |
| :--- | :--- |
| **ID** | Unique ID of the transfer node |
| **X / Y** | Planar spatial coordinates |
| **Fixed_Cost** | Fixed cost of utilizing the transfer node infrastructure |
| **Associated_Preparation_Cost** | Preparation/processing operational cost of using transfer nodes |

#### 3. Shelter Data
All capacity and tracking metrics related to regional emergency shelters are stored in this file.

| Header | Description |
| :--- | :--- |
| **ID** | Unique ID of the shelter |
| **X / Y** | Planar spatial coordinates |
| **County** | Geographic county naming designation |
| **Capacity** | Capacity of the target shelter for hosting incoming evacuees |

#### 4. Arc Data
All network optimization links and transportation parameters are stored in this file.

| Header | Description |
| :--- | :--- |
| **Origin Node** | Origin node ID of the directed network arc |
| **Destination Node** | Destination node ID of the directed network arc |
| **Fixed Cost** | Fixed overhead cost of utilizing this specific arc |
| **Variable Cost** | Variable relief transportation cost through this arc |
| **Capacity** | Flow capacity threshold of the arc |
| **Distance** | Origin-to-destination geographic distance of the arc |

---

### C. Geographic Regional Layouts

Candidate DCs and shelters are strictly considered at the geometric centroids of the selected regions, respectively. We utilize the specified zone distributions detailed below to construct our model bounds:

| Supply Region County | Population | Shelter Region County | Population |
| :--- | :--- | :--- | :--- |
| Coke | 3,285 | Angelina | 86,396 |
| Coleman | 7,684 | Atascosa | 48,981 |
| Concho | 3,303 | Bell | 370,647 |
| Cooke | 41,668 | Bexar | 2,009,324 |
| Crockett | 3,098 | Frio | 18,385 |
| Jack | 8,472 | Gonzales | 19,653 |
| Shackelford | 3,105 | Houston | 22,066 |
| Stephans | 9,101 | Kendall | 44,279 |
| Sutton | 3,372 | La Salle | 50,088 |
| Val Verde | 47,586 | Robertson | 16,757 |
| Wise | 68,632 | Smith | 233,479 |
| Travis | 1,290,188 | Walker | 76,400 |
| Washington | 35,805 | Webb | 267,114 |
