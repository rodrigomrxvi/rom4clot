# What to do in order
1) Go to LOCALIZED-POD-DL-ROM/code_LOC-POD-DL-ROM/get_and_prepare_data.ipynb. Run in order as explained until the end of the clustering section. You will have now a directory LOCALIZED-POD-DL-ROM/specie/CLASSIFICATION/MODELS/N_cluster/Data with the necessary data for training and testing.
2) Go to LOCALIZED-POD-DL-ROM/code_CLASSIFICATION and run main_training.py. This will create a directory LOCALIZED-POD-DL-ROM/specie/CLASSIFICATION/MODELS/N_cluster/my_directory/ where my_directory is specified inside main_training.py. Now you have created a Classifier, whose weights are saved in LOCALIZED-POD-DL-ROM/specie/CLASSIFICATION/MODELS/N_cluster/my_directory/weights_classifier. This procedure can be done on the laptop since it takes few minutes.
3) Go back to LOCALIZED-POD-DL-ROM/code_LOC-POD-DL-ROM/get_and_prepare_data.ipynb and run in blocks the CREATE THE N_CLUSTERS POD BASIS BASED ON FCM_LABELS section. This will create a directory LOCALIZED-POD-DL-ROM/specie/MODELS/N_pod_dl_rom/Data.
4) Send the directory LOCALIZED-POD-DL-ROM/specie/MODELS/N_pod_dl_rom/Data to the cluster, when you should have the LOCALIZED-POD-DL-ROM directory which is the copy of the local one. Be careful in creating LOCALIZED-POD-DL-ROM/specie/MODELS/N_pod_dl_rom/Data on the cluster, since there may be some intermediate directories missing.
5) In the cluster, go to LOCALIZED-POD-DL-ROM/code_LOC-POD-DL-ROM and run main_training.py. Check before running the parameters inside the script to be defined. This will create a directory LOCALIZED-POD-DL-ROM/specie/MODELS/N_pod_dl_rom/my_directory, where my_directory is specified inside main_training.py.
6) Now import on the local device the directory LOCALIZED-POD-DL-ROM/specie/MODELS/N_pod_dl_rom/my_directory, paying attention to locate it correctly.
7) Go to LOCALIZED-POD-DL-ROM/code_LOC-POD-DL-ROM and run Test.ipynb to do the testing. Be careful in Test.ipynb to give the right names of the directories of the Classifier weights and Decoder and DFNN weights, since they are different. But you decided their names when running main_training.py in code_CLASSIFICATION and in code_LOC-POD-DL-ROM.

NOTA BENE:
In order to work you need in the directory LOCALIZED-POD-DL-ROM 3 files: The DoE file with the simulations, the cell centers file with the mesh coordinates and the X_LHS_Uniform.csv file with the parameters of every simulation.