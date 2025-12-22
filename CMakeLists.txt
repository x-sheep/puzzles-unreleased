set(abcd_crop 315x315 186x186+113+112)
set(ascent_crop 336x336 195x195+71+23)
set(boats_crop 256x320 166x166+80+80)
set(bricks_crop 264x240 194x194+24+24)
set(clusters_crop 192x192 162x162+14+14)
set(crossing_crop 240x360 202x202+20+20)
set(mathrax_crop 240x240 138x138+19+83)
set(rome_crop 280x280 164x164+98+17)
set(salad_crop 280x280 152x152+120+8)
set(seismic_crop 336x336 196x196+117+21)
set(spokes_crop 432x432 220x220+146+210)
set(sticks_crop 384x384 196x196+166+70)
set(subsets_crop 432x540 182x182+124+232)

puzzle(abcd
  DISPLAYNAME "ABCD"
  DESCRIPTION "Letter placement puzzle"
  OBJECTIVE "Place letters according to the numbers. Identical letters cannot touch.")
solver(abcd)

puzzle(ascent
  DISPLAYNAME "Ascent"
  DESCRIPTION "Path-finding puzzle"
  OBJECTIVE "Place each number once to create a path.")
solver(ascent ${CMAKE_SOURCE_DIR}/matching.c)

puzzle(boats
  DISPLAYNAME "Boats"
  DESCRIPTION "Boat-placing puzzle"
  OBJECTIVE "Find the fleet in the grid.")
solver(boats ${CMAKE_SOURCE_DIR}/dsf.c)

puzzle(bricks
  DISPLAYNAME "Bricks"
  DESCRIPTION "Hexagonal shading puzzle"
  OBJECTIVE "Shade several cells in the hexagonal grid while making sure each cell has another shaded cell below it.")
solver(bricks)

puzzle(clusters
  DISPLAYNAME "Clusters"
  DESCRIPTION "Red and blue grid puzzle"
  OBJECTIVE "Fill in the grid with red and blue clusters, with all dead ends given.")

puzzle(crossing
  DISPLAYNAME "Crossing"
  DESCRIPTION "Number crossword puzzle"
  OBJECTIVE "Place each number from the list into the crossword.")
solver(crossing ${CMAKE_SOURCE_DIR}/dsf.c)

puzzle(mathrax
  DISPLAYNAME "Mathrax"
  DESCRIPTION "Latin square puzzle"
  OBJECTIVE "Place each number according to the arithmetic clues.")

puzzle(rome
  DISPLAYNAME "Rome"
  DESCRIPTION "Arrow-placing puzzle"
  OBJECTIVE "Fill the grid with arrows leading to a goal.")

puzzle(salad
  DISPLAYNAME "Salad"
  DESCRIPTION "Pseudo-Latin square puzzle"
  OBJECTIVE "Place each character once in every row and column. Some squares remain empty.")
solver(salad ${CMAKE_SOURCE_DIR}/latin.c)

puzzle(seismic
  DISPLAYNAME "Seismic"
  DESCRIPTION "Number placement puzzle"
  OBJECTIVE "Place numbers in each area, keeping enough distance between equal numbers.")
solver(seismic ${CMAKE_SOURCE_DIR}/dsf.c)

puzzle(spokes
  DISPLAYNAME "Spokes"
  DESCRIPTION "Wheel-connecting puzzle"
  OBJECTIVE "Connect all hubs using horizontal, vertical and diagonal lines.")
solver(spokes ${CMAKE_SOURCE_DIR}/dsf.c)

puzzle(sticks
  DISPLAYNAME "Sticks"
  DESCRIPTION "Line-drawing puzzle"
  OBJECTIVE "Fill in the grid with horizontal and vertical line segments.")
solver(sticks ${CMAKE_SOURCE_DIR}/dsf.c)

puzzle(subsets
  DISPLAYNAME "Subsets"
  DESCRIPTION "Set-defining puzzle"
  OBJECTIVE "Place each set once, in accordance with the subset clues.")
solver(subsets)

export_variables_to_parent_scope()
