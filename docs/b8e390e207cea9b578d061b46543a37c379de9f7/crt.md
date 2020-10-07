### changeRangeR multispecies functions in Wallace Testing instructions.
#### Please also check out the [demo video](https://youtu.be/R1cMJdNWAYo)

Instructions:
1. In R studio, run these lines of code:
```{r}
library(wallace)
run_wallace(biomodelos=TRUE)
```
2. Wallace will open in your browser. Go to the component "Occ Data" - and choose module "Query BioModelos". 
  - Enter a Genus and species for a Colombian animal name of your choice - but note it must already be in the BioModelos database (you can search the BioModelos website: http://biomodelos.humboldt.org.co/). We suggest *Alouatta palliata*.

3. For "enter API key", paste the following key: **5NbMdjylEPEN1cBCIsX9dl:3vbVvDAXQdjf40NeYHfN1g**<br> DO NOT SHARE THIS KEY WITH ANYONE OUTSIDE THE WORKSHOP.

4. The species' occurrences should appear on the map. Click on "Table" to view detailed information on each point.

5. Search for two or more additional species and choose the species name from the dropdown menu to view the loaded occurrences. We suggest as two other species: *Alouatta seniculus*, *Ateles belzebuth*

6. Continue through the rest of the modules to build a species distribution model for the species - remember to check the box "batch" when you see it to run each step for all of your species.<br>
Follow the Component and Module Guidance in each section for more information - but please skip the "Env Space"", "User SDM", "Mask", and "ChangeRR" Components.
To save time, we suggest the following choices in each component:

  - under "Env Data", you can upload user-specified 10 arc-minute data downloaded from the link on the workshop website. You don't have to select all 19 variables, you can select 1-10 or as many as you wish.
  - under "Proc Occs", use spatial thinning by 10km or skip this step.
  - under "Proc Env", use a bounding box with a 1 degree buffer and sample between 1000-10,000 background points (highest available for your area)
  - skip "Env Space"
  - under "Part Occs", use a non-spatial partition of random k-folds (2 folds)
  - under "Model", select MaxEnt, and then maxnet, L and LQH, and a regularization of range 1-2, and clamping can be either true or false.
  - under "Visualize", choose each species and then plot cloglog without a threshold. 

7. When you get to the component "Project", it is important that you project all three models to the exact same projection extent and to thresholded binary projections. For the extent, we suggest that you project to the extent of Colombia (this is the file "Col_adm0.shp" in the workshop website data downloads), and choose a minimum training presence threshold projection. This step cannot be done in batch, you will have to choose each species from the dropdown menu and then select the projection extent (Colombia shape file), and then project using the MTP threshold.

8. Skip to the "Alpha Div" Component. Select the "Richness" module and review the component and module guidance tabs. Select all three species that you modeled and projected, and click *Run* to view species richness for Colombia! If you get an error message here about projecting to the same extent, try going back to the "Project" component and add a 1 degree buffer around your polygon and reproject each species' module (like we had to do in the demo video).

9. Select the "Endemism" module. Review the module guidance tab. Select all three species you modeled and projected, and hit Run to view species endemism for Colombia!

10. If you wish, you can send your completed models to BioModelos. go to the "Reproduce" component, "BioModelos payload" module, and follow the module guidance text - you should select each species one by one to send to BioModelos.