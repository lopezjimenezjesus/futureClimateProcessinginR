## Processing future bioclimate data for species suitability models in R

Set  variables to download and process bioclimatic variables. Currently using global data due to lack of several tiles on the server. See example below:


        models <- c("CNRM-CM6-1", "BCC-CSM2-MR", "CNRM-ESM2-1", "CanESM5", "IPSL-CM6A-LR",  "MIROC-ES2L", "MIROC6",  "MRI-ESM2-0")
        ssp <-  c("126", "245", "370","585")
        time_periods <- c("2021-2040", "2041-2060", "2061-2080", "2081-2100")
        variables <- "bioc" # currently hardcoded in the function
        res <- 0.5
        path <-  here("data", "cmip6")


Also there are several custom variables. 



ext10KM<-  st_transform(st_as_sf(vect(here('data', 'input','CUTM10', 'CUTM10.shp'))), crs=4326) # change name of variable accordingly to save raster to disk (eg.: ext, esp...+ nKM)
res_folder_to_process <-"wc2.1_30s" # folder with resolution to process ( "wc2.1_2.5m" or  "wc2.1_30s")
crop_area_prefix <- "" # change accrodingly
id_column <- "CUADRICULA" # vector grid id column
id_column_name <- "ID10KM" # rename column name
