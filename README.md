# Excellente resources papers for genomics

- #### 07 September 2020 | Article | [Generation of a chromosome-scale genome assembly of the insect-repellent terpenoid-producing Lamiaceae species, Callicarpa americana](https://academic.oup.com/gigascience/article/9/9/giaa093/5902285)

- #### 28 August 2020 | Article | [The genome of the cauliflower coral Pocillopora verrucosa](https://academic.oup.com/gbe/advance-article/doi/10.1093/gbe/evaa184/5898631)

- #### 1 August 2020 | Article | [Chromosome-scale genome assembly of sweet cherry (Prunus avium L.) cv. Tieton obtained using long-read and Hi-C sequencing](https://www.nature.com/articles/s41438-020-00343-8)

- #### 8 May 2020 | Article | [Chromosome-level assembly of the horseshoe crab genome provides insights into its genome evolution](https://www.nature.com/articles/s41467-020-16180-1)
- #### 29 July 2020 | Article | [Gradual polyploid genome evolution revealed by pan-genomic analysis of Brachypodium hybridum and its diploid progenitors](https://www.nature.com/articles/s41467-020-17302-5)
- #### 1 August 2020 | Article | [A high-quality sponge gourd (Luffa cylindrica) genome](https://www.nature.com/articles/s41438-020-00350-9)
- #### 10 August 2020 | Article | [A high-contiguity Brassica nigra genome localizes active centromeres and defines the ancestral Brassica genome](https://www.nature.com/articles/s41477-020-0735-y#Sec4)
- #### 29th January 2020 | Article | [High quality 3C de novo assembly and annotation of a multidrug resistant ST-111 Pseudomonas aeruginosa genome: Benchmark of hybrid and non-hybrid assemblers](https://www.nature.com/articles/s41598-020-58319-6)
- #### 20 July 2020 | Review | [Plant pan-genomes are the new reference](https://www.nature.com/articles/s41477-020-0733-0)


# Genomics Tools

- #### [TBtools](https://github.com/CJ-Chen/TBtools) | [Paper](https://www.sciencedirect.com/science/article/pii/S1674205220301878)




# R shiny

- #### [Shiny Apps: Development and Deployment](https://www.mzes.uni-mannheim.de/socialsciencedatalab/article/shiny-apps/)
- #### [Shiny Apps: Development and Deployment Video](https://www.youtube.com/watch?v=QT3WUQu99pM)
- #### [R Recipe: Shiny Tables from Excel Templates](https://ljupcho.com/blog/shiny-excel-table-templates)



# R
- #### [Learning Statistics with R](https://learningstatisticswithr.com/)
- #### [Becoming An rvest Magician](https://zachbogart.com/post/rvest-wizardry/)
- #### [How to zoom in on a plot in R](https://datavizpyr.com/how-to-zoom-in-on-a-plot-in-r/)

- #### [Top 50 Rggplot2 visualization items](http://r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code.html)

- #### [Rboot Camp: A free online R course](https://r-bootcamp.netlify.app/)
- #### [The best books on Computer Science for Data Scientists recommended by Hadley Wickham](https://fivebooks.com/best-books/computer-science-data-science-hadley-wickham/)
- #### [flextable R package](https://davidgohel.github.io/flextable/)
- #### [PLOTTING SIGNIFICANCE ON THE TOP A BAR CHART OPTION1](https://nakedstatistics.wordpress.com/2017/05/11/plotting-significance/)
- #### [PLOTTING SIGNIFICANCE ON THE TOP A BAR CHART OPTION2](http://131.111.177.41/statistics/R/graphs2.html)
- #### [T TEST](http://www.sthda.com/english/wiki/unpaired-two-samples-t-test-in-r)
- #### [R studio data sheet](https://rstudio.cloud/learn/cheat-sheets)
- #### [R Cookbook](http://www.cookbook-r.com/)


# R Map

- #### [Interactive map with R](https://thinkr.fr/cartographie-interactive-avec-r-la-suite/)
- #### [Interactive map with R and Leaflet](https://thinkr.fr/cartographie-interactive-comment-visualiser-mes-donnees-spatiales-de-maniere-dynamique-avec-leaflet/)
- #### [Geocomputation with R](https://geocompr.robinlovelace.net/)


# R Markdown

- #### [Remedy provides addins to facilitate writing in markdown with RStudio](https://github.com/ThinkR-open/remedy) 



# Linux 

- #### [7 System Monitoring Tools for Linux to Keep an Eye on Vital System Stats](https://itsfoss.com/linux-system-monitoring-tools/)

- #### CPU and Memory usage record for a multiple algorithm process

Hello everyone.

Here is a bash script for long-reads assembly using CANU.

```
#!/bin/bash 
set -e export 
PATH='/home/raymond/devel/canu/canu/Linux-amd64/bin/':$PATH 
inputFile=$1 
outputDir=$2 
name='Epau' 
genomeSize=160kb 
threads=40 
gnuplotPath=/home/raymond/devel/gnuplot/install/bin/gnuplot 
echo $inputFile 
echo $outputDir 
canu \ -p $name \ 
-d $outputDir \ 
correctedErrorRate=$correctedErrorRate \ genomesize=$genomeSize \ 
-nanopore-raw $inputFile\
 gnuplot=$gnuplotPath \ 
useGrid=false \ maxThreads=$threads 
```

I would like to incorporate a command line in order to get CPU and memort usage every 5 mn from the begining to the end of the CANU assembly.

How could I get this info in a specific file as an output since CANU running deals with a bunch of multiple processes?

Thanks.

- ##### A1 
There are lots of different ways to attack this problem.

System stats are all in files in /proc, so to get memory usage you might parse /proc/meminfo. For CPU utilization /proc/loadavg might be what you want. Here is a link to some documentation. You could write a bash script to get these values and write to a file.

You could also add in a middle man and use the psutil package for Python and just use that

There are probably lots of other ways to do this as well

- ##### A2

f its running as a systems process, firefox for example, use

top| grep firefox --line-buffered > outfile.txt
I couldn't figure out how to get my cut to work in-line though, it seems the delimiters are scrambled after field 2.

- #### A3

answer depends on OS and environment to some extent-- is this a machine with few other users or a dedicated VM, or a shared host, and what's the OS/distribution you're running?

quick and dirty would be to run top in batch mode if that's available. Reports of the host's memory usage are available via free and vmstat -- those are useful to see if your process is eating all available memory and then failing. Unlikely with such a small genome.


Thank you for your reply. I am working on Centos 7 OS.



Probably easiest is calling top -b -n 99 -s 13 or something similar with parameters appropriate to your work.

If you are hoping for a machine-readable log and a way to summariza a proces tree by a piece of code, then more work will be necessary, but this will give you output good for human eyes to understand what's happening.


A4

[git1](https://github.com/ibest/ARC/blob/master/contrib/profilemem.R)
[git2](https://github.com/ibest/ARC/blob/master/contrib/plot_memprofile.R)









# Genomics

- #### [Great article on why consider more than one reference genome](https://www.pacb.com/blog/sequencing101pangenome/)

- ### [SIB_LongReadsAsmWorkshop_Lausanne18](https://github.com/aechchiki/SIB_LongReadsAsmWorkshop_Lausanne18/wiki)

- #### [Bioinformatics Tutotial 2019](https://angus.readthedocs.io/en/2019/toc.html)

- #### [Computational genomics tutorial 2019](https://genomics.sschmeier.com/)

- #### [Understanding, Curating, and Analyzing your Diploid Genome Assembly](https://pb-falcon.readthedocs.io/en/latest/_downloads/Kingan_DiploidGenome_ECUGM2017_BFX.pdf)

- #### [Exercise: Long Read Assembly](https://scilifelab.github.io/courses/assembly/2017-11-15/exercises/Exercise_Long_Read_Assembly.html)

- #### [Long-reads assembly lecture](https://scilifelab.github.io/courses/assembly/2017-11-15/lectures/Long_read_Assembly.pdf)


- #### [Reproducible research in Genomics](https://nbis-reproducible-research.readthedocs.io/en/course_1803/)

- #### [Conda ORF finder](https://gist.github.com/mkweskin/30e3bd57534868cccd700f4181f07103)


# Transcriptomics

- #### Deseq tuto [1](http://evomics.org/wp-content/uploads/2018/10/RNASeqWorkFlow-1.html) [2](https://rpubs.com/otienolwanga/problem_solving) [3](https://rpubs.com/mwken314/deseq2)

- #### HISAT2 HTseq DeSeq2 Rna tuto [1](http://www.cbs.dtu.dk/courses/27626/Exercises/rnaseq.php) | [2](https://pzweuj.github.io/2018/07/12/rna-seq-3.html) | [3 Hisat2 and featcount](https://bioinformaticsworkbook.org/dataAnalysis/RNA-Seq/RNA-SeqIntro/RNAseq-using-a-genome.html#gsc.tab=0) and [Deseq2](https://bioinformaticsworkbook.org/dataAnalysis/RNA-Seq/RNA-SeqIntro/Differential-Expression-Analysis.html#gsc.tab=0)

- #### [RNAseq workflow](https://github.com/Yedomon/RNAseq-workflow)

- #### [How to perform KEGG pathway analysis in R?](https://www.biostars.org/p/274514/) [Resources1](http://yulab-smu.top/clusterProfiler-book/chapter12.html) [Resources2](https://www.biostars.org/p/327039/)


- #### [Exact Tests and Plots with edgeR – Basic Differential Expression Analysis](https://morphoscape.wordpress.com/2020/09/01/exact-tests-and-plots-with-edger-basic-differential-expression-analysis/)

- #### [RNASeq lab](https://scilifelab.github.io/courses/ngsintro/1911/labs/rnaseq/lab.html)

- #### [Genomics and transcriptomics tutorials](https://scilifelab.github.io/courses/)

- #### [Annotation explained](https://www.biostars.org/p/181286/)

- #### [Fungal annotation script](https://github.com/Yedomon/Fungal_genome_annotation)

- #### [Annotation and comparative genomics script](https://github.com/Yedomon/AMPRIL-genomes)

- #### [RNA seq analysis](https://decodebiology.github.io/bioinfotutorials/rnaseq_tutorial.html)
- #### [RNA seq tuto](https://gif.biotech.iastate.edu/rnaseq-analysis-walk-through)

- #### [MA PLOT](https://www.biostars.org/p/457769/)

- #### [Complex heat map](https://github.com/kevinblighe/E-MTAB-6141)

- #### [A guide to elegant tiled heatmaps in R](https://www.royfrancis.com/a-guide-to-elegant-tiled-heatmaps-in-r-2019/)


# Chloroplast

- ### [Simple tuto](https://www.nature.com/articles/s41598-020-59204-y.pdf)


- #### [Insights Into Chloroplast Genome Evolution Across Opuntioideae (Cactaceae) Reveals Robust Yet Sometimes Conflicting Phylogenetic Topologies](https://www.frontiersin.org/articles/10.3389/fpls.2020.00729/full#B91)

- #### [Best Practices/Softwares To Calculate Ka/Ks Ratio](https://www.biostars.org/p/5817/)

- #### [The complete chloroplast genome of Stryphnodendron adstringens (Leguminosae - Caesalpinioideae): comparative analysis with related Mimosoid species](https://www.nature.com/articles/s41598-019-50620-3)

- #### [The Complete Chloroplast Genome Sequences of the Medicinal Plant Forsythia suspensa (Oleaceae)](https://www.mdpi.com/1422-0067/18/11/2288)

- #### [Comparative Analysis of the Complete Chloroplast Genomes of Five Quercus Species](https://www.frontiersin.org/articles/10.3389/fpls.2016.00959/full)

- #### [IR CONTRACTION](https://www.nature.com/articles/s41438-019-0171-1#:~:text=Compared%20with%20the%20nuclear%20genome,for%20diversity%20and%20evolution%20studies.)

- #### [PSEUDOGENE](https://peerj.com/articles/2699/?utm_source=TrendMD&utm_campaign=PeerJ_TrendMD_1&utm_medium=TrendMD)

- #### [Inspiration](https://www.researchsquare.com/article/rs-20050/v1)

- #### [Dr swati 1](https://peerj.com/articles/9448/)

- #### [Dr swati 2](https://www.mdpi.com/2223-7747/9/5/568/htm)



# R spatial

- #### [r map tuto 1](https://datavizm20.classes.andrewheiss.com/example/12-example/) [content](https://datavizm20.classes.andrewheiss.com/content/) [video](https://www.youtube.com/watch?v=Opzwtegvuv4&t=743s)
- #### [r map tuto 2 create a shp file from data frame ](https://datacarpentry.org/r-raster-vector-geospatial/10-vector-csv-to-shapefile-in-r/)
- #### [r map tuto 3 raster manip](https://datacarpentry.org/r-raster-vector-geospatial/)
- #### [r map tuto 4](https://www.earthdatascience.org/courses/earth-analytics/spatial-data-r/make-maps-with-ggplot-in-R/)
- #### [r map tuto 5](http://zevross.com/blog/2018/10/02/creating-beautiful-demographic-maps-in-r-with-the-tidycensus-and-tmap-packages/)
- #### [r map tuto 6 sf test](https://gist.github.com/andrewheiss/8e514355d75aac1a7d6b91a67b896f20) [fig](https://twitter.com/andrewheiss/status/1291431466556100608) [data](https://github.com/jvangeld/ME-GIS)
- #### [reading and writing spatial data in r in r](https://mgimond.github.io/Spatial/reading-and-writing-spatial-data-in-r.html)
- #### [Drawing beautiful maps programmatically with R, sf and ggplot2 — Part 2: Layers](https://www.r-spatial.org//r/2018/10/25/ggplot2-sf-2.html)
- #### [Geospatial Health Data: Modeling and Visualization with R-INLA and Shiny](https://www.paulamoraga.com/book-geospatial/)


# Rogeria longiflora
 
- #### March 2012 | [Germination and growth requirements of Rogeria longiflora – Medicinal plant of the Namib Desert](https://www.sciencedirect.com/science/article/pii/S0254629911001797)
- #### [RARE AND INTERESTING PLANTS OF THE NAMIB DESERT](https://journals.co.za/docserver/fulltext/veld/80/4/2395.pdf?expires=1599199452&id=id&accname=guest&checksum=A132124BA5604D1262C81C2E69E6C821)
- #### [Phylogeny of Pedaliaceae and Martyniaceae and the Placement of Trapella in Plantaginaceae s. l.](https://www.ingentaconnect.com/content/aspt/sb/2015/00000040/00000001/art00030)
- #### [Pedaliaceae](https://link.springer.com/chapter/10.1007/978-3-642-18617-2_17)
- #### [Wood Anatomy of Martniaceae and Pedaliaceae](https://scholarship.claremont.edu/cgi/viewcontent.cgi?referer=https://scholar.google.com/&httpsredir=1&article=1506&context=aliso)
- #### [Dispersal Biology of Desert Plants : Restriction of Dispersal in Time](https://link.springer.com/chapter/10.1007/978-3-662-03561-0_8)
- #### [Dewinteria](http://opus.sanbi.org/bitstream/20.500.12143/4207/2/van%20Jaarsveld_2007_PEDALIACEAE%2C%20Dewinteria%2C%20a%20new%20semisucculent%2C%20cliff-dwelling%20genus%20endemic%20to%20the%20Kaokoveld%2C%20Namibia.pdf)
- #### [Ecogeography and taxonomy of Rogeria J. Gay ex Delile (Pedaliaceae)](https://www.tandfonline.com/doi/abs/10.1080/00837792.2013.867609)
- #### [Rogeria species](http://www.ville-ge.ch/musinfo/bd/cjb/africa/resultat.php?efNom=rogeria&efFamille=&projet%5B%5D=FSA&projet%5B%5D=FTA&projet%5B%5D=FNA&projet%5B%5D=BDM&langue=an&pbRecherche=Search)


# Ceratotheca triloba

- #### [basic description](https://onlinelibrary.wiley.com/doi/pdf/10.1111/j.1467-8748.2011.01747.x?casa_token=GyWXoq2XXfMAAAAA:IPI77qhB7znxhHSl3EASdnGYbxNrctsA7U-YE84wYtiYgLhOBCqyT_mXABhp056dOyQLZTymddbgUunT)



# Fungal Genomics 

- #### [Inspiration paper 1 for Graph color respect with R  ](https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-020-06871-w)
- #### [Code and script Fungal annotation assemblies and so on](https://gitlab.gwdg.de/alice.feurtey/genome_architecture_zymoseptoria)


# NNS-LRR genes 

- #### [Inspirational paper 1](https://bmcplantbiol.biomedcentral.com/articles/10.1186/s12870-020-02576-0#Sec16)
- #### [Dioscorea](https://www.frontiersin.org/articles/10.3389/fgene.2020.00484/full)
- #### [Cassava](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4422547/pdf/12864_2015_Article_1554.pdf)
