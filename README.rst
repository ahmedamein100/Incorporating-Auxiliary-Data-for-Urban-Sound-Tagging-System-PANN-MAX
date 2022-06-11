Incorporating Auxiliary Data For Urban Sound Tagging System (PAN-MAX) 
=====================================

This is the source code for DCASE 2020 Task 5 Iqbal submission, and we applied a modification on it.

Please read our thesis for more details about the system, it will be included with name 'Thesis.pdf'.

Iqbal paper ---> http://dcase.community/documents/challenge2020/technical_reports/DCASE2020_Iqbal_38_t5.pdf


.. contents::
Prefrence
------------
We suggest to use anaconda enviroment to run the code.

You should have at least 4GB GPU (if you have less than 8GB GPU, you have to decrease the batch size(from default.conf file); due to shortage of meomry)


Requirements
------------

This code requires Python version >=3.6.

To install the required dependencies, run::

    pip install -r requirements.txt

SONYC-UST v2 dataset will be used , you should install
bash dependency to download the dataset ,run the following 
command from the root directory of the project to download
the dataset::

    $ scripts/download_dataset.sh

This dataset will be downloaded in this directory ``_dataset/``.

__ https://zenodo.org/record/3873076


Run Code
--------

To run the experiments, there are several bash scripts
available in this directory  ``_script/`` folder,
run this command::

    $ scripts/run.sh
    

Note that files will be created in a folder with directory
``_workspace``.

To show the result run this command::
    
   $ scripts/evaluate.sh


Modification
------------
 So our modification is to change the pooling type of cnn10 model,
 so the exist pooling type at the moment is the max-pooling as mentioned 
 in the paper. To change the pooling type, you can edit 
``_task5/pytorch/qkcnn.py`` file ( from line 34 to line 40)
 by changing pool_type parameter::
    
    
    pool_type = "avg" -----> average pooling
    pool_type = "max" -----> max pooling


Configuration
-------------
You can find all configuration in (default.conf) file, 
you can edit them according to your preference(EX: batch size, mel bins ect.).


Copyright
---------
Copyright (c) 2020, Turab Iqbal
