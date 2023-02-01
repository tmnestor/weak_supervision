# weak_supervision
Using snorkel to Label a Dataset
## Translation of IHC to labelling functions
The notebook set_IHC_dict.ipynb:
- extracts 404 teradata sql case statements from a text file file
- strips comments from IHC case statements
- assigns the 404 case statemnts to the 99 separate categories
- stores the 101 case statements in a nested  IHC_dict dictionary indexed by the wre code, to facilitate down stream conversion to snorkel labelling functions
- IHC_dict is then serialised as a json file

The notebook wre_snorkling.ipynb:
- reads in the  IHC_dict serialised json file 
- converts relevant IHC_dict fields programmatically into regex search patterns
- defines a factory function to create snorkel labelling functions given any one (or all) of the 99 wre codes
- applies all 101 labelling functions in a prescribed order to implement IHC heirachies (there are two separate heirachies)

## Set Up
- colab setup cell should not be run on local host (obviously!)
  - requirements.txt is needed to setup colab
- run following to setup makbook pro (only)
  - nlp_env.yml is needed to setup on a macbook m1 pro
  - conda env create -n nlp_env -f nlp_env.yml





