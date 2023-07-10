# EM Cmap Scoring Tool

## :shipit: Overview

The EM Cmap Scoring Tool is a desktop application developed to automatically assess Concept Maps using Traditional and Categorical Scoring Methods. By default the tool was developed to assess Entrepreneurial Mindset Concept Maps however, by changing the Wordbank default file it can be used to assess Concept Maps from other subjects. To do so, please refer to the section "Creating a New WordBank"

### Table of contents:
[Installing EM Cmap Scoring Tool](#wrench-installing-em-cmap-scoring-tool)

[User's Manual](#book-users-manual)

[Creating a New WordBank](#floppy_disk-creating-a-new-wordbank)

[Including a New Codebook](#orange_book-including-a-new-codebook)

## :wrench: Installing EM Cmap Scoring Tool
- Please go over and click the [**EM_Cmap_Scoring_Tool_Launcher.zip**](https://github.com/RMejiaE/EM-Cmap-Scoring-Tool/blob/main/Phase_5/EM_Cmap_Scoring_Tool_Launcher.zip) at the top of this page, then clik on the *Download* option on the right side of the screen.
- Under your computer folder, right-click **EM_Cmap_Scoring_Tool_Launcher.zip** and select *Extract all*.
  - :warning: Please do not go diectly into the .zip folder
  
| ![imagen](https://user-images.githubusercontent.com/78668372/233404342-ba3c8d10-e2c7-437e-a0da-82f20dab5c04.png) |
| :-: |
| Figure 1: .zip extraction procedure |

- Open the resulting folder after the extraction and double click on the **Cmap_Scoring_Tool_Launcher** application file to run the program (Figure 2).

| ![imagen](https://user-images.githubusercontent.com/74432387/252414286-d4566db1-8365-40d9-adc7-01254f520460.png) |
| :-: |
| Figure 2: Launch program |

- If Windows alerts you because of the application being unknown, please click on *Run anyway* or *More information* and then *Run anyway*

| <img src="https://user-images.githubusercontent.com/78668372/229847812-d8e15832-8819-401c-af6d-07d6c938bb0a.png" width=50% height=60%> |
| :-: |
| Figure 3: Protection window |

## :book: User's Manual
### :mailbox_with_mail: Input Files Type
The EM Cmap Scoring tool was designed to read CXL files exported from CmapTools (https://cmap.ihmc.us/), a free software to create concept maps. 
After creating a concept map in CmapTools, the map should be exported as CXL (File -> Export Cmap As -> CXL File...)

### :crystal_ball: Main Graphical User Interface

| ![imagen](https://user-images.githubusercontent.com/74432387/252414649-71da88b1-9c81-4f96-a788-0f2138b8e537.png) |
| :-: |
| Figure 4: EM Cmap Scoring tool GUI UPDATE |

After lauching the EM Camp Scoring Tool, a main GUI is displayed (Figure 4) with the following elements:  

1. Radio button to select the Scoring method. You can choose either "Traditional" or "Categorical" 
2. Text box to write the root concept
3. *Browse* button to select the .cxl files to score.
4. *Browse* button to select the path and filename for the Results Report.
5. *Help* button that opens a window to explain how to prepare the Cmaps files and how to use the Scoring Tool.
6. *Codebook* nutton to open a PDF with the descrition of the Categories in the WordBank for the Categorical Method
7. *Run* button to execute the scoring.

### :bar_chart: Scoring Methods 

### Traditional Scoring Method
This method assigns a score based on the number of concepts (NC), the number of hierarchies (NH), the highest hierarchy (HH), and the number of crosslinks (NCL) between concepts.
NC is the number of concepts that have connections with other concepts in the map; NH are the number of branches (hierarchies) that come from the root concept; HH is the hierarchy (branch) with the largest number of concepts; and NCL are the number of connections between concepts from different hierarchies.
The formula to get the score based on these metrics is: Score = (NC) + 5*(HH) + 10*(NCL)

Figure 5 shows an example a concept map with 9 concepts. Figure 6 shows the identification of the different hierarchies and the highest hierarchy (HH). Figure 7 highlights the crosslink in this concept map. For this example, the NC will correspond to 9, NH is 3, the HH will be hierarchy 2 with 3 levels, and NCL value corresponds to 1.

| ![imagen](https://user-images.githubusercontent.com/78668372/229846688-053cee04-0534-417b-a71f-7421fccae00b.png) | ![imagen](https://user-images.githubusercontent.com/78668372/229847229-deb70aed-940f-49b2-89c1-6a0e4ce86f47.png)    | ![imagen](https://user-images.githubusercontent.com/78668372/229847398-aec3cc25-ae7f-4eb0-b5ba-2de266ecda3a.png) |
| :-: | :-: | :-: |
| Figure 5: EM Cmap example with number of concepts (NC) identification. | Figure 6: Number of hierarchies (NH) and highest hierarcy (HH) identification. | Figure 7: Number of crosslinks (NCL) identification. |

### Categorical Scoring Method
The number of concepts (NC) is obtained by counting all the concepts, excluding the root concept, present in the Cmap. The number of categories (NCAT) is obtained by classifying the concepts present into each of the categories and counting the ones that contain at least one concept. For the case of Entrepreneurial Mindset (EM), the cateogries were defined by the [Word Bank](https://github.com/RMejiaE/EM-Cmap-Scoring-Tool/blob/main/Phase_2/WordBank.csv) developed by the research team members. Lastly, the number of interlinks (NIL) is obtained by counting the connections between paired concepts that are from different categories.

| ![imagen](https://user-images.githubusercontent.com/78668372/229618016-94668494-1f69-418b-9535-5520c98fda32.png) | ![imagen](https://user-images.githubusercontent.com/78668372/229618225-0650527c-9952-4f7c-af26-fb7dd75c95c5.png) | ![imagen](https://user-images.githubusercontent.com/78668372/229618261-4721051f-92f2-4f9b-9fdc-54e18428638a.png) |
| :-: | :-: | :-: |
| Figure 10: EM Cmap example with number of concepts (NC) identification. | Figure 11: Number of categories (NCAT) identification. | Figure 12: Number of interlinks (NIL) identification. |

Figure 10 shows an example of a concept map with 9 concepts. After listing the concepts, they are categorized using a word bank (Figure 11) and finally interlinks are identified (Figure 12).
For this example, the NC will correspond to 9, NCAT will be 3, and NIL value corresponds to 2.

### Categorical Scoring Method
This method identifies the number of concepts (NC) present in the Cmap, then classifies the concepts into categories, and lastly, it calculates the number of concepts in each category to finally compute the number of categories (NCAT) that contain at least one concept. After that, it calculates the number of  connections between concepts of different categories, better known as interlinks (NIL). The score is meassure by the level of complexity (CO) of the Cmap.

CO = NC*(NIL/NCAT)

On Figure 6, each concept would be assigned a number depending on the category for the NC and NCAT calculation, and them the connection between **Foundations** and **Floor** would be checked to see if the two concepts are from different categories.

### 🔮 Manual Categorization GUI 

When the Categorical Method is selected, the Scoring Tool will display a new window “Manual Concept Categorization” with the concepts in the Concept Map that were not found in the Wordbank file. The scoring tool will pre-assign these concepts to the category of the higher concept in their hierarchy. In the “Manual concept Categorization” window the user can leave the preassigned category or select a different category from a scrolling menu (Figure 5). 

| ![imagen](https://user-images.githubusercontent.com/78668372/245650502-b4fe9877-406d-4909-8f53-5d93dfcc1b3f.png) |
| :-: |
| Figure 5: Manual Categorization GUI dropdown menu update |

To accept the preassigned or new category, the radio button must remain in “Accept all assignments” and the user must press “Continue” (Figure xxxx).
The user can also select “Reject all assignments and leave all concepts [that were not found in the Wordbank] in No category”. In this case, those concepts will not count for the Score.   

|![image](https://user-images.githubusercontent.com/74432387/252420985-c84d36d8-6e3e-480f-ae1a-00096d6246e8.png)|
| :-: |
| Figure xxxx: Accept or Reject categories for concepts not found in the Wordbank |

## :floppy_disk: Creating a New WordBank

## :orange_book: Including a New Codebook
