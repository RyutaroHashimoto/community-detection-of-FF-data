# Community detection of FF-data (2020)

The datasets in this repository represent annotations of module labels obtained by clustering *FF-data*. 

*FF-data (Flow of Foreigners-Data)* is a collection of datasets in which travel pathways of foreign travelers in Japan are recorded annually. It is distributed by the [Ministry of Land, Infrastructure, and Transport](https://www.mlit.go.jp/sogoseisaku/soukou/sogoseisaku_soukou_fr_000022.html).
Each dataset includes 47 prefectures and 34 ports in Japan. Currently (Jul. 2020), datasets from 2014 through 2017 are available.

We used the framework of the memory networks (1st- and 2nd-order Markov networks) to represent the datasets in FF-data as networks and performed community detection (i.e., clustering) using the map equation (Infomap). 
Please find the paper by M. Rosvall et al. for the details of the memory networks and the map equation: 
[Rosvall, M., Esquivel, A., Lancichinetti, A. et al. "Memory in network flows and its effects on spreading dynamics and community detection," Nat. Commun. 5(1) (2014)](https://www.nature.com/articles/ncomms5630)

The figure below shows popular transitions that appear in the four largest modules detected by applying the map equation to the 2nd-order Markov networks in 2017.

<div align="center">
<img src="https://github.com/RyutaroHashimoto/community_detection_of_FF-data/blob/master/img/ModuleMapFigure.png"  width="500px" alt = "Japanese map showing a brief overview of the classified elements of traveler pathways.">
</div>

Please find the following paper for further details of FF-data and its community detection: 

T. Kawamoto and R. Hashimoto, "Identifying macroscopic features in foreign visitor travel pathways," *in preparation* (2020).
	

## Contents
The following files are included:

1. README.md (this file).
2. README_ja.md : README file writen in Japanese.
3. id_list.csv : List of `id` of prefectures and ports used in this dataset.
	- `id` : Code that represents a prefecture or a port.
	- `name_j` : Name of a prefecture or a port in Japanese.
	- `name_e` : Name of a prefecture or a port in English.
4. 1st_order : Results of the community detection of the 1st-order Markov networks (i.e., a direct network representations) using the map equation.
	- `id` : Code of a node.
	- `name` : Name of a node in English.
	- `module_index` : Index of a module that a node belongs to.
5. 2nd_order : Results of the community detection of the 2nd-order Markov networks using the map equation.
	- `prior_id` : Code of a prior node.
	- `prior_name` : Name of a prior node in English.
	- `destination_id` : Code of a destination node.
	- `destination_name` : Name of a destination node in English.

## Note
`module_index` in a dataset is assigned independently for each year. 
For example, in the 1st-order dataset, Hokkaido belongs to module 1 in 2014 and 2015. However, this does not mean Hokkaido belongs to the same Module 1 for two years. 

## Citation

Please cite the following when you use the annotated data in this repository:

T. Kawamoto and R. Hashimoto, "Identifying macroscopic features in foreign visitor travel pathways," *in preparation* (2020).
