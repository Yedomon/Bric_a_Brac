# Excellente resources for genomics



[Large structural variations in the haplotype-resolved African cassava genome](https://www.biorxiv.org/content/10.1101/2021.06.25.450005v1.full)


![img](https://www.biorxiv.org/content/biorxiv/early/2021/06/26/2021.06.25.450005/F3.medium.gif)



[Code available for R graphs]()








Today 02 july 2021 on bioachive | [A chromosome-level genome sequence of a model chrysanthemum: evolution and reference for hexaploid cultivated chrysanthemum](https://www.biorxiv.org/content/10.1101/2021.06.28.450068v1.full)



![img](https://www.biorxiv.org/content/biorxiv/early/2021/06/29/2021.06.28.450068/F3.medium.gif)










Pacbio [Twitter](https://twitter.com/PacBio/status/1410318485104873475)

> Plant genome assembly can be v. difficult. It took >10 years to assemble the genome of one #barley variety! See how @SchreiberMona , Martin Mascher of @IPKGatersleben & co used HiFi sequencing to generate accurate & complete assemblies in a few days .


Plantae [interpretation](https://plantae.org/faster-and-easier-access-to-genetic-information-with-long-read-sequencing/)

Background: The genome encodes the entire genetic information of an organism. It is stored as a DNA nucleotide sequences in the nucleus of each cell of an organism. The DNA is organized into chromosomes, structures large enough to be visible under a microscope. The genome of the crop plant barley consists of about five billion nucleotides. Sequencing and assembling a genome means reading out all its nucleotides and arranging them into a computer-readable text. Genome assembly used to be very difficult. It took over ten years to assemble the genome sequence of one barley variety. Genomes differ between the individuals of one species and we can learn a lot about diversity in our crops by comparing genomes of different varieties. Researchers that want to study many genomes need a fast and reliable method for sequence assembly.

Question: We wanted to know if a new method for DNA sequencing, accurate long-read sequencing, can make genome assembly faster and easier.

Findings: We used the PacBio HiFi sequencing method to generate accurate long-reads of the barley genome and assembled the reads into sequences representing entire chromosomes. We also made genome assemblies from other types of sequence reads generated with alternative methods such as short reads or long-reads with high error rates. When we compared the different assemblies to each other, the HiFi assembly performed best. It represented the largest fraction of genes, also those that are present in multiple, nearly identical copies. The HiFi assembly also captured almost all of non-coding and highly repetitive sequences between genes. Importantly, the HiFi method was very fast so that we were able to generate accurate and complete genome sequences in a few days.

Next steps: We will use HiFi sequencing to assemble genomes of more cultivated varieties and wild relatives of barley. We expect to find genetic variants, for example in diseases resistance genes, that may help enrich the genetic diversity of barley.

Martin Mascher, Thomas Wicker, Jerry Jenkins, Christopher Plott, Thomas Lux, Chu Shin Koh, Jennifer Ens, Heidrun Gundlach, Lori B Boston, Zuzana Tulpová, Samuel Holden, Inmaculada Hernández-Pinzón, Uwe Scholz, Klaus F X Mayer, Manuel Spannagl, Curtis J Pozniak, Andrew G Sharpe, Hana Šimková, Matthew J Moscou, Jane Grimwood, Jeremy Schmutz, Nils Stein (2021) Long-read sequence assembly: a technical evaluation in barley. Plant Cell. [doi](https://doi.org/10.1093/plcell/koab077)




a Benchmarking approach was used to find out the best assembly. With the canu assembly, they set a scaffolding with bionano followed by gap filling with nanopore assembly contigs the perform Hi-C


> The CCS_canu contigs were scaffolded with BionanoSolve (https://bionanogenomics.com/support/software-downloads/) version 3.5_12162019 using the “hybridScaffold_DLE1_config.xml” parameter set. Prior to gap filling, the set of scaffolds was filtered using the following criteria: scaffolds not assigned to chromosomes using Hi-C and POPSEQ data as described in the TRITEX pipeline were discarded unless they fulfilled the following three conditions (1) their length was ≥50 kb, (2) they were not reported to be “bubbles” by Canu, and (3) they had 10-folded coverage with CCS reads as report by Canu *OR* carried genes not present in scaffolds assigned to chromosomes. Gap filling was done with TGS-Gapcloser (Xu et al., 2019, https://github.com/BGI-Qingdao/TGS-GapCloser) using ONT_smartdenovo contigs as “reads” for closing gaps. The parameters “–min_match 5000 –min_idy = 0.5 –ne” were used. The script TGS-GapCloser.sh was modified to use the following Minimap2 parameters: “-K 10G -I 10G -f 0.005 -x asm5” for assembly-to-assembly alignment and exclusion of highly repetitive minimizers. Gap sequence in the scaffolds before and after gap filling was determined with seqtk (https://github.com/lh3/seqtk, parameters “cutN -g -n 0”). Gap-filled scaffolds were used as input for pseudomolecule construction using the TRITEX pipeline as described by Monat et al. (2019). Hi-C data of (Mascher et al., 2017) were used for ordering and orienting scaffolds (ENA accession PRJEB14169). POPSEQ markers (Mascher et al., 2013) and GBS loci mapped in the Morex × Barke recombinant inbred lines reported by Mascher et al. (2017) were aligned to preliminary pseudomolecules using Minimap2 (Li, 2018) and the order and orientations of scaffolds in the distal 10 Mb of each chromosome arm were inspected and corrected manually




So I discovered an algorithm that can handle gapfilling [TGS-GapCloser](https://github.com/BGI-Qingdao/TGS-GapCloser) with long reads data. Awesome discoveriing.

I can use that for gap filling with our nextdenovo as input like Mascter used ONT_smartdenovo contigs assembly as reads for gap closing. Besides it is available on conda. So I can use it easily in NABIC. So great! Thank you God for guiding me through this.





![img](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/plcell/PAP/10.1093_plcell_koab077/3/m_koab077f4.jpeg?Expires=1627866555&Signature=GybBghtvGZGupzeBKbdk51FCpP-oMDpbN6fz6rUf4q7VfVlG9JMwJL7fX9YU5sg4QYVBE1XHAc5YLmO8R8WWqbIxkNglBryDgXxvjJ3rPgs-Edklu~N3ddlP6WkbwRCgZwXrtEvFAnzlKzWG3VWgXNxAHvv04wY3S4RNUOIliaduuWDUMMnJm9TWepTV9IXRKo3zCiuYURaMejYeVNErSHRdhzTjGDNIdCryslWfI9q48kPw6~jUZbXbJzAZLDa-KIHZVH-4EJ5UKq7ZlVjgDup0bMCxGpT08LP8XH9GBUtA61d19wuphCzv7AxEdXW2aahP~BMU5GiWnEcfahRrXA__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)




Genome evolution and divergence of common and tepary bean.

![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41467-021-22858-x/MediaObjects/41467_2021_22858_Fig1_HTML.png?as=webp)





Quelqu'un qui vend ses services en bioinformatique. Il me faudra faire un truc pareil aussi




https://www.gringene.org/



An other paper on African crop without African authors


[Large structural variations in the haplotype-resolved African cassava genome](https://www.biorxiv.org/content/10.1101/2021.06.25.450005v1)






A bon review qui montre le besoin de se resaisir en Afrique sur le plan genome


[Lessons from 20 years of plant genome sequencing: an unprecedented 
resource in need of more diverse representation](https://www.biorxiv.org/content/10.1101/2021.05.31.446451v1.full.pdf)








Une bonne inspiration pour faire un truc pareil avec le Fusarium oxysporum species




[Long-reads are revolutionizing 20 years of insect genome sequencing](https://academic.oup.com/gbe/advance-article/doi/10.1093/gbe/evab138/6307268)



![img](https://www.biorxiv.org/content/biorxiv/early/2021/02/15/2021.02.14.431146/F1.large.jpg?width=800&height=600&carousel=1)


[Code available](https://github.com/pbfrandsen/insect_genome_assemblies)



out the 14 june 2021:  Peach genome and population genomics

[Population-scale peach genome analyses unravel selection patterns and biochemical basis underlying fruit flavor](https://www.nature.com/articles/s41467-021-23879-2)


![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41467-021-23879-2/MediaObjects/41467_2021_23879_Fig1_HTML.png?as=webp)


si how the found sv and follow the way to make it for sesame













## [The nearly complete genome of Ginkgo biloba illuminates gymnosperm evolution](https://www.nature.com/articles/s41477-021-00933-x)


![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41477-021-00933-x/MediaObjects/41477_2021_933_Fig1_HTML.png?as=webp)











## [The draft chromosome-level genome assembly of tetraploid ground cherry (Prunus fruticosa Pall.) from long reads](https://www.biorxiv.org/content/10.1101/2021.06.01.446499v1)





![img](https://www.biorxiv.org/content/biorxiv/early/2021/06/01/2021.06.01.446499/F6.large.jpg?width=800&height=600&carousel=1)










[The Earth BioGenome project: opportunities and challenges for plant genomics and conservation](https://onlinelibrary.wiley.com/doi/full/10.1111/tpj.14631)


![img](https://onlinelibrary.wiley.com/cms/asset/6d456c6f-4dd7-4216-9a65-e408c0f217d1/tpj14631-fig-0002-m.jpg)






[Advancing crop genomics from lab to field](https://www.nature.com/articles/s41588-021-00866-3?hash=83f37f73-82e3-4669-ad63-50c192ab98b6&utm_medium=social&utm_source=facebook)


![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41588-021-00866-3/MediaObjects/41588_2021_866_Fig3_HTML.png?as=webp)


[Genome sequence of Gossypium herbaceum and genome updates of Gossypium arboreum and Gossypium hirsutum provide insights into cotton A-genome evolution](https://www.nature.com/articles/s41588-020-0607-4#Sec10)


![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41588-020-0607-4/MediaObjects/41588_2020_607_Fig1_HTML.png?as=webp)


[Wolfberry genomes and the evolution of Lycium (Solanaceae)](https://www.nature.com/articles/s42003-021-02152-8#Sec17)


![img](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs42003-021-02152-8/MediaObjects/42003_2021_2152_Fig3_HTML.png?as=webp)









[Abiotic stress through time](https://nph.onlinelibrary.wiley.com/doi/full/10.1111/nph.17367)

Tansley insight by Kathleen K. Markham  and Kathleen Greenham


![img](https://nph.onlinelibrary.wiley.com/cms/asset/4ac61aed-275e-4bc4-8e43-9f5bf72bab53/nph17367-fig-0002-m.png)




Why does wild rice possess superior tolerance to salinity? Solis et a;. studied the effects of salinity in the ancestral rice O. rufipogon and the inbred varieties of cultivated rice under field conditions.




[Sodium sequestration confers salinity tolerance in an ancestral wild rice](https://onlinelibrary.wiley.com/doi/abs/10.1111/ppl.13352)



[Back to the Wild: On a Quest for Donors Toward Salinity Tolerant Rice](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7098918/)



![img](https://www.frontiersin.org/files/Articles/524985/fpls-11-00323-HTML/image_m/fpls-11-00323-g003.jpg)






[How Do Plants Deal with Dry Days?](https://kids.frontiersin.org/articles/10.3389/frym.2017.00058)


![img](https://www.frontiersin.org/files/Articles/275076/frym-05-00058-HTML/image_m/main.jpg)



[Create beautiful scientific infographics with no effort](https://mindthegraph.com/)



![img](https://mindthegraph.com/assets/img/home/react/header_humanized_image.png)



[Lessons from 20 years of plant genome sequencing: an unprecedented resource in need of more diverse representation](https://www.biorxiv.org/content/10.1101/2021.05.31.446451v1)


> ...... the field has been dominated by affluent nations in the Global North, despite a wide geographic distribution of sequenced species. We identify multiple inconsistencies between the range of focal species and the national affiliation of the researchers studying the plants, which we argue are rooted in colonialism--both past and present. Falling sequencing costs paired with widening availability of analytical tools and an increasingly connected scientific community provide key opportunities to improve existing assemblies, fill sampling gaps, and, most importantly, empower a more global plant genomics community.







[Hybrid de novo genome assembly of red gromwell (Lithospermum erythrorhizon) reveals evolutionary insight into shikonin biosynthesis](https://www.nature.com/articles/s41438-020-0301-9)




![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41438-020-0301-9/MediaObjects/41438_2020_301_Fig2_HTML.png?as=webp)





From my Cell Biology Professor



[Hi-C analysis: from data generation to integration](https://link.springer.com/article/10.1007/s12551-018-0489-1)


[Genomes of 13 domesticated and wild rice relatives highlight genetic conservation, turnover and innovation across the genus Oryza](https://www.nature.com/articles/s41588-018-0040-0)


[PacBio Sequencing and Its Applications](https://www.sciencedirect.com/science/article/pii/S1672022915001345?via%3Dihub)




Just found this paper on wedy rice published in 2020.  [Diverse genetic mechanisms underlie worldwide convergent rice feralization](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-020-01980-x)





![img](https://media.springernature.com/full/springer-static/image/art%3A10.1186%2Fs13059-020-01980-x/MediaObjects/13059_2020_1980_Fig2_HTML.png?as=webp)












[A new duck genome reveals conserved and convergently evolved chromosome architectures of birds and mammals](https://academic.oup.com/gigascience/article/10/1/giaa142/6039068)


[Code availability](https://github.com/ZhouQiLab/DuckGenome)  | [circos plot](https://github.com/ZhouQiLab/DuckGenome/tree/master/circos_plot) 


![img](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/gigascience/10/1/10.1093_gigascience_giaa142/3/m_giaa142fig1.jpeg?Expires=1623406895&Signature=44bCpD9MMowMGoLQFLCu8on0NFvV1gtYRnWQteZIlzmzMSYK9uzUxgdK-~EUWRCsbiC-i1NtLpupxr4~dzDPMJmeC5n7taqVwfZiwRD850UiTMcRw3~L5XnWBalJWPB76EU2bc5kV~0CAzW9vyGzbKKOQgIs6YsNfYZTjfGj4-XUX-q92lPGIsQq4Ejy9TEpF-BAdCye7N4bgiCwpAShJ2aY8IKfgDg~0euP-FV70XQJ5MlUG6ekNfSYwnZhtn~CY09fM00nexl4IEwwfmDbo-K5Rl50WIDYt8l~R41b5YfMuBNVQxb6cFMXtpDI8Zn4VGUaIsIis64a3F1z2-HYSg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)





[Liming Cai 蔡黎明](https://scholar.google.com/citations?hl=en&user=VgQdugwAAAAJ&view_op=list_works&sortby=pubdate)


![img](https://d2r55xnwy6nx47.cloudfront.net/uploads/2021/04/Liming_Cai_v3-1720x1128.jpg)


[Deeply Altered Genome Architecture in the Endoparasitic Flowering Plant Sapria himalayana Griff. (Rafflesiaceae)](https://www.cell.com/current-biology/fulltext/S0960-9822(20)31897-2?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0960982220318972%3Fshowall%3Dtrue#%20)


![img](https://d2r55xnwy6nx47.cloudfront.net/uploads/2021/04/Rafflesia_arnoldii_2880_Lede.jpg)

[Nice press release infographics](https://www.quantamagazine.org/dna-of-giant-corpse-flower-parasite-surprises-biologists-20210421/)


![img](https://d2r55xnwy6nx47.cloudfront.net/uploads/2021/04/Sapria_himalayana.jpg)


Infography

![img](https://d2r55xnwy6nx47.cloudfront.net/uploads/2021/04/Giant-flowers-1.svg) | ![img](https://d2r55xnwy6nx47.cloudfront.net/uploads/2021/04/Giant-flowers-2.svg)



- #### [Assembly of a pan-genome from deep sequencing of 910 humans of African descent](https://www.nature.com/articles/s41588-018-0273-y)


![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41588-018-0273-y/MediaObjects/41588_2018_273_Fig1_HTML.png?as=webp)



- #### [Whole-genome analysis of giraffe supports four distinct species](https://www.cell.com/current-biology/fulltext/S0960-9822(21)00546-7)



![img](https://els-jbs-prod-cdn.jbs.elsevierhealth.com/cms/attachment/994eaf9b-16a3-4648-9a0f-bd569bfb1abc/gr2.jpg)


- #### [Phased diploid genome assemblies and pan-genomes provide insights into the genetic history of apple domestication](https://www.nature.com/articles/s41588-020-00723-9)

![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41588-020-00723-9/MediaObjects/41588_2020_723_Fig1_HTML.png?as=webp)






- #### [Genome of Tripterygium wilfordii and identification of cytochrome P450 involved in triptolide biosynthesis](https://www.nature.com/articles/s41467-020-14776-1#change-history)


![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41467-020-14776-1/MediaObjects/41467_2020_14776_Fig1_HTML.png?as=webp)



- #### [Genome-enabled discovery of anthraquinone biosynthesis in Senna tora](https://www.nature.com/articles/s41467-020-19681-1)


![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41467-020-19681-1/MediaObjects/41467_2020_19681_Fig1_HTML.png?as=webp)



Published: 28 April 2021 | [Chromosome-scale assembly and analysis of biomass crop Miscanthus lutarioriparius genome](https://www.nature.com/articles/s41467-021-22738-4#Sec12)



![IMG](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41467-021-22738-4/MediaObjects/41467_2021_22738_Fig1_HTML.png?as=webp)


[Recent Applications of RNA Sequencing in Food and Agriculture](https://www.intechopen.com/online-first/recent-applications-of-rna-sequencing-in-food-and-agriculture)


[Sequencing, Assembly and Annotation of the Whole-Insect Genome of Lymantria dispar dispar, the European Gypsy Moth](https://watermark.silverchair.com/jkab150.pdf?token=AQECAHi208BE49Ooan9kkhW_Ercy7Dm3ZL_9Cf3qfKAc485ysgAAAscwggLDBgkqhkiG9w0BBwagggK0MIICsAIBADCCAqkGCSqGSIb3DQEHATAeBglghkgBZQMEAS4wEQQMtdETOGSDTi0vZvAaAgEQgIICepDu-2PGLJyxkwB9_cfUq3VZVyYlnCppiUeWlMYG4WS2-bgSWyHsWnZTEdJUSonLcNTjFlskF7JAOexBHS63Q-dOqCnyO_GYFlQ5x8LNAYkzN0NCV7BgvyWxPnFt4O6wE0RXh-X6PQhNQX_oGEvYFNiB90CjC4e-TqSITEXFB9aE6j3dMuumji_f7dX_lQCC1ZNo8FbUJ3cw-6xnLBvqrmyUNYqLnDT8Vt84CbyCPHZ0H8FJER9wNA48B6VNOjc-KesvT99Q0UxTaZlpseapCcDZw8RNxp5H5JQHLYZwOn3XH0osaDsdg11LxdL1dL32gmwJuEhJ9xw5VCU3-_flKYDKIeQ4XAN-Tglig0XC_XlbJnD9uE0iZwEzOFv-Fc-rVJyr9nOGzHOrwJfAvhsaui-HZFFmNMVK6L5EQAbmlSc8A822narupzTzHDBk12lKZ2rRIXPev9OX_cYLy-JPfPfknLe_kOg11z61FzFmaQ8YQ5H6qa4i5SYEClRA1DgN1pGm2ojj2Cd0nGSVUlfDh7xSfV7Atc2T5j5GUXme7AeG24GQ3ocndB4Z2_PNLZYy1BP7WoPpcTktlokjqBinC5sUN59DJ6zI5p_8TimlMIkExzVPGo3fduSns-Vg9I9h0V2s5iWstREA2vZ5FOPiEWCaIhhpY6XcRKak2XLj5OIXXV0egq38GKPU-wxHRNTJvic0XZxYmMk8kFqr-seKxF1r1lfDZ0EPETJdWRgflAz3Mo2Yhq74JVpYgo_59YHSWIRWX9ScRnoocPGCxvPJBpy4H2-x6q3U_WZemiSZoruaHz9hYurq0XHsaKDeVVISoUctU8nN4k6YE_Q)










[The domestication of Cucurbita argyrosperma as revealed by the genome of its wild relative](https://www.nature.com/articles/s41438-021-00544-9#Sec9)



> Anchoring the reference genomes into pseudomolecules
We aimed to improve the genome assemblies of argyrosperma and sororia, which were assembled in 920 scaffolds14 and 817 contigs, respectively. Thus, we generated PacBio corrected reads from the published PacBio RSII reads of argyrosperma (NCBI SRA accession SRR7685401) and the PacBio Sequel reads of sororia (sequenced for this study at the University of Washington PacBio Sequencing Services) using CANU71. The macrosynteny of Cucurbita genomes is largely conserved between species, so we performed a reference-guided scaffolding step using RaGOO18 to anchor the genome assemblies of argyrosperma and sororia into pseudomolecules. We used the genome assembly of C. moschata as the reference genome for RaGOO and we used the PacBio corrected reads of each taxon to detect and correct misassemblies, using a gap size of 2600 bp for chromosome padding (i.e., we filled the gaps between contigs with 2600 stretches of Ns, corresponding to the average gap length of the argyrosperma genome assembly). The chromosome numbers in both assemblies were assigned in correspondence to the genome assembly of C. moschata.








[Genome-wide association mapping in maize: status and prospects](https://link.springer.com/article/10.1007/s13205-021-02799-4)

![img](https://media.springernature.com/full/springer-static/image/art%3A10.1007%2Fs13205-021-02799-4/MediaObjects/13205_2021_2799_Fig1_HTML.png?as=webp)




Factors affecting GWAS




![IMG](https://media.springernature.com/full/springer-static/image/art%3A10.1007%2Fs13205-021-02799-4/MediaObjects/13205_2021_2799_Fig2_HTML.png?as=webp)








[Pathway-based analysis of anthocyanin diversity in diploid potato](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0250861)


[Leaf nutrient content and transcriptomic analyses of endive (Cichorium endivia) stressed by downpour-induced waterlog reveal a gene network regulating kestose and inulin contents](https://www.nature.com/articles/s41438-021-00513-2)



30 April 2021 | [Comparative transcriptomic analysis reveals the regulatory mechanism of the gibberellic acid pathway of Tartary buckwheat (Fagopyrum tataricum (L.) Gaertn.) dwarf mutants](https://bmcplantbiol.biomedcentral.com/articles/10.1186/s12870-021-02978-8)




01 May 2021 | [Whole-genome resequencing of Osmanthus fragrans provides insights into flower color evolution](https://www.nature.com/articles/s41438-021-00531-0#Sec2)




> Fresh, healthy leaves were harvested from the best-growing individuals and immediately frozen in liquid nitrogen, followed by preservation at −80 °C in the laboratory prior to DNA extraction. High-quality genomic DNA was extracted using a modified Cetyltrimethyl Ammonium Bromide method16. For genome sequencing, single-molecule real-time (SMRT) libraries were constructed and sequenced using a PacBio Sequel II instrument (Pacific Biosciences, Menlo Park, CA, USA) at Frasergen Bioinformatics Co., Ltd. (Wuhan, China). For resequencing, 1 μg DNA per sample was used as the input material, and sequencing libraries were generated using the VAHTS Universal DNA Library Prep Kit for MGI (Vazyme, Nanjing, China) following the manufacturer’s recommendations. Library quantification and size measurement were performed using a Qubit 3.0 Fluorometer (Life Technologies, Carlsbad, CA, USA) and a Bioanalyzer 2100 system (Agilent Technologies, CA, USA). Subsequently, libraries of 122 accessions were constructed and sequenced on an MGI-SEQ 2000 platform at Frasergen Bioinformatics Co., Ltd.







[Genetic diversity structure of western-type carrots](https://bmcplantbiol.biomedcentral.com/articles/10.1186/s12870-021-02980-0)




![img](https://media.springernature.com/full/springer-static/image/art%3A10.1186%2Fs12870-021-02980-0/MediaObjects/12870_2021_2980_Fig7_HTML.png?as=webp)



29 April 2021 | Nature editorial | Importance of transparency in Life Sciences


[Good research begins long before papers get written](https://www.nature.com/articles/d41586-021-01167-9)



![img](https://media.nature.com/lw800/magazine-assets/d41586-021-01167-9/d41586-021-01167-9_19117598.jpg)





During the University of Oregon/PacBio Virtual Launch Party I discovered Yim Lab at University of Nevada. A lab dedicated to plant genomics. Here is the [website](https://www.plantbioinformatics.org/)

Nice teaching material [here](https://plantgenomicslab.github.io/BCH709/)





Something interesting in Hazelnut genome project | There are ~20 species of Hazelnut.


- Corylus heterophylla Fisch. | China | Published in 2021 | Illumina + Nanopore + Hi-C | [Paper](https://academic.oup.com/gigascience/article/10/4/giab027/6237163)

- Corylus mandshurica | China | Published in 2021 | Illumina + Nanopre + Hi-C | [Paper](https://www.nature.com/articles/s41438-021-00495-1#Sec11)

- Corylus avellana L. | Turkey | Published in 2020 | Illumina + Nanopore + Hi-C | [Paper](https://onlinelibrary.wiley.com/doi/10.1111/tpj.15099)

- The Turkish guy published the chloroplast genome paper first in 2019 before the whole genome in 2020 | [Paper](https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-019-6253-5) 
 

Breaking News!!!

28 April 2021

Arang Rhie et al. vient de publier une semi version de 17 species dans le cadre du pipeline officiel 
[Towards complete and error-free genome assemblies of all vertebrate species](https://www.nature.com/articles/s41586-021-03451-0)

![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41586-021-03451-0/MediaObjects/41586_2021_3451_Fig1_HTML.png?as=webp)


The pipeline

![image](https://user-images.githubusercontent.com/45568831/116543774-43bac900-a929-11eb-98be-6b90b6dfc1dc.png)




And the special issue of Nature dedicated to the phase I of the VGP project


[https://www.nature.com/collections/cabiagjdfj/](https://www.nature.com/collections/cabiagjdfj/)




A dedidacted phase assembly from FALCON using Hi-C data 


[Extended haplotype-phasing of long-read de novo genome assemblies using Hi-C](https://www.nature.com/articles/s41467-020-20536-y) | [PPT](https://ucdavis-bioinformatics-training.github.io/2018-Dec-Genome-Assembly/falcon-phase/FALCON-Phase-talk-2018.pdf)


Heng Li also proposed Hi-C phasing with paired-end short reads in two FASTQ files [hifiasm](https://github.com/chhylp123/hifiasm)






By reading the first paper from genome collection of Molecular Plant journal, I noticed Qing Zhao, a specialist for metabolite investigation in plant. He was a PI for an other genome project published in the Gigascience sister genome journal Gigabyte. This guy has a good skill for metabolic pathway work. Interestingly, he used the same approaches (yeast assay and gene cloning) to prove the role of the identified genes. More interestingly, he applied a time divergence gene inference with his gene of interest by setting available date. Amaizing guy. See [paper 1](https://www.cell.com/molecular-plant/fulltext/S1674-2052(19)30131-5#fig3) in 2019 



![img](https://marlin-prod.literatumonline.com/cms/attachment/b18cf9a1-cb49-4f54-806a-5891dcd77e03/gr2.jpg)




[Paper 2](https://gigabytejournal.com/articles/14) in 2021.


![img](https://gigabytejournal.com/admin/apis/public/article_shell/uploads/article_files/Gigabyte/Gigabyte/2021/gigabyte14/gigabyte14-g005.jpg)



But when I wanted to get the web link of the paper 2 by pasting the title in google, I found another team from China that worked on the same genome but with another metabolic pathway. They published in Nature communications. [Such a good paper](https://www.nature.com/articles/s41467-020-19253-3). Finally after the nature paper was published on 20 February 2020, and corrected on 15 October 2020, Qing Zhao team submited on 10 October 2020 and get published on 28 February 2021 in Gygabyte as a data release.



![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41467-020-14776-1/MediaObjects/41467_2020_14776_Fig1_HTML.png?as=webp)




For linkage map construction | The criteria of SNP filtration after SNP calling


> To ensure the quality of genetic map, the polymorphic SNPs were filtered according to the following rules: (1) filtering SNPs with sequencing depths of < tenfold between both parents, (2) screening genotypes covering at least 70% of all offspring, (3) filtering the SNP markers with segregation distortion test P < 0.01 by Chi-square test. In the end, genetic linkage maps were constructed from the SNP genotypes in both RILs using the JoinMap software version 4.0.


From [High-density mapping for gray leaf spot resistance using two related tropical maize recombinant inbred line populations](https://link.springer.com/article/10.1007/s11033-021-06350-9)



An other one 

> SNPs were identified based on the polymorphic SLAF tag information using the software program GATK 3.7.0 (McKenna et al. 2010) and SAMtools 1.9 (Li et al. 2009). The intersection of SNPs determined by GATK and SAMtools were considered as potential high-quality SNPs. Samples with coverage less than 10-fold were removed, and consistent SNPs were selected using the criteria of minor allele frequency (MAF) > 0.05 and integrity > 0.8.


From [SNP detection and population structure evaluation of Salix gordejevii Y. L. Chang et Skv. in Hunshandake Sandland, Inner Mongolia, China](https://link.springer.com/article/10.1007/s12298-021-00994-4)



BREAKING News, whole genome resequencing and evolutionnary studies example with lettuce case 


[Whole-genome resequencing of 445 Lactuca accessions reveals the domestication history of cultivated lettuce](https://www.nature.com/articles/s41588-021-00831-0) 


A press release [here](https://www.wur.nl/en/newsarticle/The-DNA-of-lettuce-unravelled-in-6000-years-from-weed-to-beloved-vegetable.htm)


[Code available](https://github.com/popgenome/lettuce2020)


![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41588-021-00831-0/MediaObjects/41588_2021_831_Fig1_HTML.png?as=webp)

















Review : [Epigenetics and epigenomics: underlying mechanisms, relevance, and implications in crop improvement](https://link.springer.com/article/10.1007/s10142-020-00756-7)


![img](https://media.springernature.com/full/springer-static/image/art%3A10.1007%2Fs10142-020-00756-7/MediaObjects/10142_2020_756_Fig2_HTML.png?as=webp)


Example of epigenomics paper | [The chromosome-level Hemerocallis citrina Borani genome provides new insights into the rutin biosynthesis and the lack of colchicine](https://www.nature.com/articles/s41438-021-00539-6)




![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41438-021-00539-6/MediaObjects/41438_2021_539_Fig1_HTML.png?as=webp)



[PCAtools](https://github.com/kevinblighe/PCAtools)


nice infography from Ensembl on [twitter](https://twitter.com/ensembl/status/1386294156755095552)

![img](https://github.com/Yedomon/Bric_a_Brac/blob/master/genes.jpg)



Celebrating the #DNADay21 by sharing an illustration of our high molecular weight DNA extraction [protocol](https://www.protocols.io/view/plant-dna-extraction-and-preparation-for-ont-seque-bcvyiw7w)

It worked for [yam](https://www.mdpi.com/2073-4425/11/3/274/htm), [A. thaliana](https://www.biorxiv.org/content/10.1101/2021.03.03.433755v2), and many other plants

#DNADay2021 #Genomics #PlantSci #SciComm

![img](https://github.com/Yedomon/Bric_a_Brac/blob/master/dna%20prep.jpg?raw=true)


When ready consider to work with 

Genomics & Cell Characterization Core Facility
SHIPPING ADDRESS: University of Oregon/GC3F,
1318 Franklin Blvd, Room 273 Onyx Bridge
Eugene , OR 97403
Office: Klamath Hall, 288
P: 541-346-5170 P: 541-346-5130

Contact Us

genomics@uoregon.edu



The cost of pacbio hifi is [here](https://gc3f.uoregon.edu/pacbio-sequencing-2)

![here](https://gc3fstorage.uoregon.edu/IMAGES/PacBio-prices(FY21).PNG)



Make chromosome without reference 



[AFLAP: assembly-free linkage analysis pipeline using k-mers from genome sequencing data](https://link.springer.com/article/10.1186/s13059-021-02326-x)




Just found Jordan A Dowell from Plantae community [youtube video](https://youtu.be/TT6phnTw8_w) | He wrote a nice paper on [GWAS](https://academic.oup.com/jhered/article/110/3/275/5371358?login=true) | I was impress by the circular manathan plot of GWAS. So I google and I found resource [of Yin Lin](https://github.com/YinLiLin/CMplot) | [Yan ](https://www.r-graph-gallery.com/101_Manhattan_plot.html)

Other provider in UK


[Edinburgh Genomics](https://genomics.ed.ac.uk/services/long-read-sequencing)


[Earlham Institute](https://www.earlham.ac.uk/genomics-services)





I just see today a history telling about cucumis


In 2019 a chinese group generated a high-quality assembly of the melon [Payzawat](https://www.cell.com/iscience/pdf/S2589-0042(19)30430-4.pdf) using a combionation of short-read sequencing, single-molecule real-time sequencing, Hi-C, and a high-density genetic map.


![img](https://ars.els-cdn.com/content/image/1-s2.0-S2589004219304304-gr1.jpg)

This year 2021, another chinese group generated [Cucumis metuliferus and Cucumis melo](https://onlinelibrary.wiley.com/doi/10.1111/tpj.15279) genome were released 

So finaly there are two melo and one metuliferus. It will be nice tutorial for my thesis. 





a free zoom named [wonder](https://www.wonder.me/)

[Telomere-to-telomere gapless chromosomes of banana using nanopore sequencing](https://www.biorxiv.org/content/10.1101/2021.04.16.440017v1?rss=1)










[A chromosome‐level genome of the spider Trichonephila antipodiana reveals the genetic basis of its polyphagy and evidence of an ancient whole-genome duplication event](https://academic.oup.com/gigascience/article/10/3/giab016/6178709)

The spider

![img1](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/gigascience/10/3/10.1093_gigascience_giab016/1/m_giab016fig1.jpeg?Expires=1621198014&Signature=L9fw~HAsv4ZZmMiw7Lp-0Shegpr9FCGSB91lhRcPs6WnPnMv4zX4unuJG97l~GIm~mf~jlRkeZjv8XLZtoRcwJILmAhX6rXOSarfLihRJtO7UbWCjX0dgcqoXHdaZxFKipu7m~QOl9VDH88EyZdZ-VdbyTto3tGw73stpIX4CYLU7kGr-S7Yfni0R5ce25O3sBJXyZRfbUsTfC5gx95MiJy1EeXxBAfwCFh2pnkk~L0AMHZzb947wA-GPtuhkK-s-JxwZC-G34x8TLU3L2yfpqIHSe044rR1G-upVdI9SYBf8xZaA-NESp7F1Re8NiG1jiCB~SqYFpjL0ySWuF3H3A__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)


The comparative analysis


> Orthologous gene clusters were classified using OrthoFinder v2.3.8 (OrthoFinder, RRID:SCR_017118) [59] across the well-annotated and well-assembled genomes of 10 species covering representative Chelicerata lineages along with T. antipodiana: 1 Scorpiones (Centruroides sculpturatus, GCA_000671375.2), 5 Acari (Dermatophagoides pteronyssinus, GCA_001901225.2; Galendromus occidentalis, GCA_000255335.1; Tetranychus urticae, GCA_000239435.1; Varroa destructor, GCA_002443255.1; I. scapularis, GCA_002892825.2), 3 Araneae (P. tepidariorum, GCA_000365465.3; S. mimosarum, GCA_000611955.2; T. clavipes, GCA_002102615.1), and 1 Xiphosura (Tachypleus tridentatus). With the exception of T. tridentatus [60], most protein sequences were downloaded from the NCBI database.

> To infer the phylogeny of these species, the protein sequences of 236 single-copy genes were separately aligned using MAFFT v7.394 (MAFFT, RRID:SCR_011811) [61] based on the L-INS-I strategy. The resulting alignments were trimmed using trimAl v1.4.1 (trimAl, RRID:SCR_017334) [62] to remove sites of unclear homology using the heuristic method “automated1.” The resulting alignments were concatenated using FASconCAT-G v1.04 [63]. Genes that violated the models were removed prior to tree inference. Finally, maximum likelihood reconstructions were performed using IQ-TREE v2.0.7 (IQ-TREE, RRID:SCR_017254) [64] with extended model selection followed by tree inference, model set by LG, with the number of partition pairs for the rcluster algorithm, replicates for ultrafast bootstrap, and Shimodaira–Hasegawa approximate likelihood ratio tests being 1,000, 10, and 1,000, respectively.

> The divergence time was estimated with MCMCTree within the package PAML v4.9j (PAML, RRID:SCR_014932) [65] using parameters with independent clock rates; BDparas-related birth, death, and sampling rates of 1, 10, and 0.1, respectively; kappa_gamma of 62; alpha_gamma of 11; rgene_gamma of 2,201; and sigma2_gamma of 1,101. Fossil records were derived from the paleobiodb database [66] and the recently described fossils Eramoscorpius brucensis [67] and Parioscorpio venator [68], with Chelicerata (genus Paleomerus, 516‒541 million years ago [Mya]), Parasitiformes (Deinocroton draculin, 93.5‒145.5 Mya), and Arachnopulmonata (E. brucensis and P. venator, 435‒439 Mya).

Café v4.2.1 (CAFÉ, RRID:SCR_005983) [69] was used to identify the likelihood of gene family expansion and contraction using the single birth–death parameter λ and a P-value threshold of 0.01. GO and KEGG functional enrichment of the significantly expanded families was assessed using Tbtools v1.045 [70].


![img2](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/gigascience/10/3/10.1093_gigascience_giab016/1/giab016fig3.jpeg?Expires=1621563080&Signature=b15DpMwBCL1lgjzvp3oibIXHdM5ZTB2ivFBvSoGvq6odl6SrORGf0jrbUiNQnEHmPXviVCZVZkPjWcNZ67tdcsbSpLFbjt8VczjYWc6nwCG6wdiMMlIDdUKBJ8DbqUNE5Aeuv4p22VxQKmRTA-VgDkbayp2R5foypvGtkmglKK3vLKlhvZC620VU7KBcZlwI1yZCyGNwEhH66qCErzRUnYhUezR5UbXHjAoV72SzAhqz2B9wsPsIKlzGEW-loWtfBixSAt8fl2IgtHdKtZ1h~RxmiJ12cpey8nxYvwZv8bM4vDKN8brxd4lfCZZh-cMAi98l7lYUsbC65EBuV3yeAQ__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)





[Genome-wide association and transcriptome analysis of root color-related genes in Gossypium arboreum L.](https://link.springer.com/article/10.1007/s00425-021-03622-3)

[High density genetic map and quantitative trait loci (QTLs) associated with petal number and flower diameter identified in tetraploid rose](https://www.sciencedirect.com/science/article/pii/S2095311920634165)


[Can omics deliver temperature resilient ready-to-grow crops?](https://www.tandfonline.com/doi/full/10.1080/07388551.2021.1898332)


![img](https://www.tandfonline.com/na101/home/literatum/publisher/tandf/journals/content/ibty20/0/ibty20.ahead-of-print/07388551.2021.1898332/20210407/images/large/ibty_a_1898332_f0001_c.jpeg)

[HiC-Hiker: a probabilistic model to determine contig orientation in chromosome-length scaffolds with Hi-C](https://academic.oup.com/bioinformatics/article/36/13/3966/5830260)

New paper in Nature communications with data and code availability | Check the paper [here](https://www.nature.com/articles/s41467-020-20508-2?hss_channel=tw-2884394676&utm_campaign=phasebook&utm_medium=email&_hsmi=119964439&_hsenc=p2ANqtz-_XwfQ3wbOy5yKr5My-cn5DT5r5u4tC5LR2Li4Ey57yzX2xGok-2SZmXgsw0UNoeQLU0KvFwDZaZD_p-iy8CtjIZOLZ-g&utm_content=119964439&utm_source=hs_email#code-availability) |The title is *Chromosome-level genome assembly of Ophiorrhiza pumila reveals the evolution of camptothecin biosynthesis*| [The github repository](https://github.com/amit4mchiba/Codes-and-script-for-Ophiorrhiza-pumila-genome-manuscript) | [Zenodo](https://zenodo.org/record/4279079#.YG5sZc_itPY)

The pipeline

![pipe](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41467-020-20508-2/MediaObjects/41467_2020_20508_Fig1_HTML.png?as=webp)

The comparative genomics

![comp](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41467-020-20508-2/MediaObjects/41467_2020_20508_Fig3_HTML.png?as=webp)



Data release GigaByte | [The genome of Tripterygium wilfordii and characterization of the celastrol biosynthesis pathway](https://gigabytejournal.com/articles/14)

> J'ai aime le design transcriptome, la procedure pour l'asembly et le evolutionnary analysis.n Aussi le volet Bionano. Cela me sera utile apres pour ma redaction.


Data release GigaByte |  [Chromosome-level genome assembly of the humpback puffer, Tetraodon palembangensis](https://gigabytejournal.com/articles/17) | [Protocol.io](https://www.protocols.io/view/protocols-for-34-chromosome-level-genome-assembly-bkczksx6) | [Preprint](https://www.preprints.org/manuscript/202008.0694/v1)


[Improved maize reference genome with single-molecule technologies](https://pubmed.ncbi.nlm.nih.gov/28605751/)

inspiration for Goenbaek qualitty genome 

![img](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fnature22971/MediaObjects/41586_2017_BFnature22971_Fig1_HTML.jpg?as=webp)




lavender genome [genome paper in 2021](https://www.nature.com/articles/s41438-021-00490-6.pdf) | but before in 2020 only the spike transcriptome [paper](https://www.nature.com/articles/s41598-020-63950-4#Sec11)


a collection pf horticulture plant [genome](Horticultural plant genomes)





[Genome-wide identification of mlo genes in the cultivated peanut (Arachis hypogaea L.)](https://link.springer.com/article/10.1007/s10681-021-02792-1)

> Mildew Locus O may be applicable to pearl millet ----> try it !










[Genome assembly and population genomic analysis provide insights into the evolution of modern sweet corn](https://www.nature.com/articles/s41467-021-21380-4)



![ng](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41467-021-21380-4/MediaObjects/41467_2021_21380_Fig1_HTML.png?as=webp)









[A route to de novo domestication of wild allotetraploid rice](https://www.cell.com/cell/fulltext/S0092-8674(21)00013-1?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0092867421000131%3Fshowall%3Dtrue)







![ds](https://els-jbs-prod-cdn.jbs.elsevierhealth.com/cms/attachment/24f490d4-be9d-4a44-8904-4d9127a8cb3d/fx1.jpg)


[Stay-Green Sorghum to the Rescue](https://www.croptrust.org/blog/stay-green-sorghum-to-the-rescue/)


> “Wild species and landraces have developed traits that enable them to deal with extreme environments, but in some cases these are missing from more advanced varieties,” says Kilian. “With the onset of climate change—and more heat waves and droughts, more severe weather—finding these traits and using them to breed more resilient crops is essential.”




[Top banana: developing varieties that resist disease](https://www.nature.com/articles/d41586-020-03194-4)



![d](https://media.nature.com/w1172/magazine-assets/d41586-020-03194-4/d41586-020-03194-4_18572046.jpg)


[comprehensive review of scaffolding methods in genome assembly](https://academic.oup.com/bib/advance-article-abstract/doi/10.1093/bib/bbab033/6149347)





[A Pipeline for Non-model Organisms for de novo Transcriptome Assembly, Annotation, and Gene Ontology Analysis Using Open Tools: Case Study with Scots Pine ](https://bio-protocol.org/e3912)


[Mapping and Validation of Major Quantitative Trait Loci for Resistance to Northern Corn Leaf Blight Along With the Determination of the Relationship Between Resistances to Multiple Foliar Pathogens of Maize (Zea mays L.)](https://www.frontiersin.org/articles/10.3389/fgene.2020.548407/full)




[Genome sequence and genetic diversity analysis of an under-domesticated orphan crop, white fonio (Digitaria exilis)](https://academic.oup.com/gigascience/article/10/3/giab013/6168810)




![image](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/gigascience/10/3/10.1093_gigascience_giab013/1/giab013fig1.jpeg?Expires=1619700858&Signature=p2nzO8NIimGkT6Ff6460CcPVaDQeXWN0XY0pX0diScQldR~b2SCzrbUWbfaKfM1VZ~XHYSsxhmWRh9lXShRoa~aNktL1PYkkf8fxAagvmubrDJDIR41iYZUjCwfQBT-pXZuwrrY08SATfCPk9TRxgbsfdCccV8TG54An3iI19fVnwDmTQEHbdX1fCQt1MwRIYKRS52m7xnAh8KG9MXbrccevci~dCmeoWjr3vFyzTov9y9wMWMOSV4bq6sPUOrNnLbAz0Ey0SROx5AoEUyCipIYChfgIRp0W-nNVfK5F2QHbVeWQjIKY0HTDX2vUXonkB3oyvlUeTRcoXJVJ2bOz-A__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)

[Population genomics and haplotype analysis in spelt and bread wheat identifies a gene regulating glume color](https://www.nature.com/articles/s42003-021-01908-6)




[Sorghum and Pearl Millet as Climate Resilient Crops for Food and Nutrition Security](https://www.frontiersin.org/research-topics/14666/sorghum-and-pearl-millet-as-climate-resilient-crops-for-food-and-nutrition-security#articles)



#### [triannotate](https://southgreenplatform.github.io/trainings/trinityTrinotate/TP-annotation/)



#### New Journal [Gigabyte](https://gigabytejournal.com/) [Smartdenovo](https://gigabytejournal.com/articles/15) was published there! Awesome!


[The genome of Tripterygium wilfordii and characterization of the celastrol biosynthesis pathway](https://gigabytejournal.com/articles/14)


#### [wendel lab script in genomics](https://github.com/Wendellab)

[New nanopore sequencing kit shows 99% raw single-molecule accuracy](https://nanoporetech.com/about-us/news/new-nanopore-sequencing-chemistry-developers-hands-set-deliver-q20-99-raw-read?utm_campaign=K19016%20Digest%20Light&utm_medium=email&_hsenc=p2ANqtz-_5mFig-6JGDyqY95Dzk-XsgcXvxzrfcuI7853pUAQ_mK8daU6ArTONXrIpNPXt2P7DEsagJhel3AVL4GDYlh30_V1a5g&_hsmi=113957430&utm_content=113955780&utm_source=hs_email&hsCtaTracking=9c29bb50-5573-40d6-95e0-cfaf9418f369%7C30e43cbe-e09c-48fa-be2f-3edb38fec038)









![fig](https://nanoporetech.com/sites/default/files/s3/news/Zymo_Q20EA_alignment_accuracy_overall.png)


#### [The genome of Magnolia biondii Pamp. provides insights into the evolution of Magnoliales and biosynthesis of terpenoids](https://www.nature.com/articles/s41438-021-00471-9)


#### [Chromosome-scale genome assembly of Cucumis hystrix—a wild species interspecifically cross-compatible with cultivated cucumber](https://www.nature.com/articles/s41438-021-00475-5)





#### WGDI Whole genome duplication identification tools | [github](https://github.com/SunPengChuan/wgdi) | [conda version](https://bioconda.github.io/recipes/wgdi/README.html) | [documentation](https://wgdi.readthedocs.io/en/latest/index.html)





##### Inspirational paper for using RNA seq to find genes of interest related to oil biosynthesis 

[Identification of genes associated with the biosynthesis of unsaturated fatty acid and oil accumulation in herbaceous peony ‘Hangshao’ (Paeonia lactiflora ‘Hangshao’) seeds based on transcriptome analysis](https://link.springer.com/article/10.1186/s12864-020-07339-7)







#### [Chromosome-Scale Assembly and Annotation of the Macadamia Genome (Macadamia integrifolia HAES 741)](https://academic.oup.com/g3journal/article/10/10/3497/6053545)

![images](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/g3journal/10/10/10.1534_g3.120.401326/6/m_3497f1.png?Expires=1617027548&Signature=GZA5z3H3m27aYBFK6JDf6XNl8wSisyiWMyQFyqj8O7zFoDFn4zP29-OpZ6HtPLkvn-E6Rs1DnI1yzKcJY9I3ds3M7yYLQZw9UvDM5BJ3NG9YCxMGEvo0QKbQiKi~f15KO7KinsVPcoGrm91FnAoDU~k06Dgaz8tlCXESSLL9kynQFtglhrWzSCju05EiFzKlaKu66NO83Y0zkCnC~CmXzPVxxkAWJ~HtAPA8kyNnIWgM~BO977n~F2vTvVBYOaFghSS31kVEbDgV4LFZHwLgIK-Uf1uI2AU8~TtqICYJZvZTLHLYzYvHbx98n2VGTFXlSqvJt~xOL2zut9KocJVvFw__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)





Code availaibility


```python

BBMap version 36.62: ktrim = r k = 23 mink = 11 hdist = 1 tpe tbo maxns = 1 minlen = 50 maq = 8 qtrim = rl trimq = 20

LoRDEC version 0.4: lordec-correct -2 input_for_read_correction.fastq -k 19 -S out.stat.txt -s 3 -T 12 -i PacBio_filtered_reads.fasta -o out.pacbio.corrected.fasta

MaSuRCA version 3.2.1. Default parameters except: NUM_THREADS = 16, JF_SIZE = 20000000000 (jellyfish hash size)

L_RNA_scaffolder: blat -t = dna -q = dna scaffolds_gapClosed_min1000.fa Trinity.fasta transcript.vs.macaAssembly.psl -noHead -out = psl

ALLMAPS version 0.7.7: Default parameters

Jellyfish version 2.0: jellyfish count -t 14 -C -m 27 -s 8G -o 27mer_maca_illumOnly_out <all Illumina-only WGS fastqs > jellyfish histo -t14 27mer_maca_illumOnly_out> 27mer_maca_illumOnly_out.histo

findGSE: Default parameters

GenomeScope version 2.2.6:kmer length 27, read length 125bp, Max kmer coverage 1000

Trinity, version 2.0.3: Trinity–seqType fq–max_memory 100G –left reads_S_R1_clean.fq,reads_F2_R1_clean.fq,reads_YL_R1_clean.fq–right reads_S_R2_clean.fq,reads_F2_R2_clean.fq,reads_YL_R2_clean.fq–CPU 8

RepeatModeler version 2.0.1. Default parameters

RepeatMasker version 4.0.9. Default parameters

MAKER, version 2.31.10. Default parameters except: Gene prediction methods Augustus and SNAP (trained with previously generated macadamia gene models); AED score = 0.40; Minimum protein length: = 50 amino acids

BUSCO version 3.0.2: busco -i proteins.fasta -l viridiplantae_odb10 -m proteins -o output_name

Minimap2 version 2.17. Default parameters (paftool.js bundled with Minimap2): minimap2 -ax sr ref_assemblyfasta fastq1stReadPair fastq2ndReadPair > ref_readPairs_aln.paf; k8 paftools.js stat ref_readPairs_aln.paf > alignment_mapstats

GATK HaplotypeCaller version 4.1.4.1: gatk–java-options “-Xmx8g” HaplotypeCaller -R refGenome.fasta -I input.bam -O output.g.vcf.gz -ERC GVCF -heterozygosity 0.01

GATK GenotypeGVCFs version 4.1.4.1: gatk–java-options “-Xmx4g” GenotypeGVCFs -R refGenome.fasta -V input.g.vcf.gz -O output.vcf.gz–heterozygosity 0.01

GATK VariantsToTable version 4.1.4.1: gatk-4.1.4.1/gatk–java-options “-Xmx8g” VariantsToTable -V output.vcf.gz -F CHROM -F POS -F TYPE -F REF -F ALT -F HET -GF GT -GF AD -O output_genoGVCF.table.txt.



```

#### [Kew Tree of Life Explorer](https://treeoflife.kew.org/)


#### Haplotype-resolved diverse human genomes and integrated analysis of structural variation | excellent coloring scheme for high quality figure publication [suppl.](https://science.sciencemag.org/content/sci/suppl/2021/02/24/science.abf7117.DC1/abf7117-Ebert-SM.pdf)


#### [Bytesize 4: GitHub contribution basics by Alexander Peltzer - Boehringer Ingelheim Pharma GmbH & Co. KG, Germany](https://nf-co.re/events/2021/bytesize-4-github-contribution-basics) | [Video](https://youtu.be/gTEXDXWf4hE)

- #### [Molecular Basis of Disease Resistance in Banana Progenitor Musa balbisiana against Xanthomonas campestris pv. musacearum](https://www.nature.com/articles/s41598-019-43421-1)


- #### [The genome of the tegu lizard Salvator merianae: combining Illumina, PacBio, and optical mapping data to generate a highly contiguous assembly ](https://academic.oup.com/gigascience/article/7/12/giy141/5202467)

Busco


![bUSCO1](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/gigascience/7/12/10.1093_gigascience_giy141/1/giy141fig3.jpeg?Expires=1617077350&Signature=T2s~YKXlwkstsdQk0hAq7PANh5ytg8W4zgLE6NeQqiekvBROOSXgbu4N-qVEanBO9NxZttddD8t0epixoboahl9LCXt~9RcX875EO70qdfk8q3R4aRty4yHdgdUxa6pd3Q0N0WHjV6RIuq2-Kp-aV7LKu7VloiMQySG9BNx5Ewvv0xD59MLuYV-0I0H2IMvOecFS6cJB6616IgbmEajlbyfZO5IVgdk6DJhwF0BBMg8yd5wuMhkOS1QGBflxEybU58lPfnSBmANCkSJ1aWNpHPlM8lSSkIRVT1GLttScXSlK9DN4SkAzZkryjTe3I8hz-ZZIFyGkPMq7kOE7rKTrtg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)

Repeat


![Repeat](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/gigascience/7/12/10.1093_gigascience_giy141/1/giy141fig5.jpeg?Expires=1617077446&Signature=dvlL1M9GyOOHYyzuievTsrpyyJKkjXBczHCF6J1SspS2N79ZiSw7H8GtFqtZC9eNFjh3pZOcZaNh4PPRfYa8erzzgftqbWyqrUZIiG5jybnNuReHvNPqRXFjo7gV7I4ZOIGPZZC~wGcJDq-UW2CijSB9AV2zDGhtR6TTykbq7SP00DJKegXukrm6KQkl7Grdq8zoGkB6CnkjsvUNobER~FWvW-SiLgyPnKuFcOJW4lD~O7xVE1WJl-cTxoBeaoTA-UyMeSkowFvF~glcsbZWnZ4mFUe7WHWFYAaOjxYX2z7PxsYdPAxIjHy6KaEbqCFP9t7Enu4W3BeUwAzzTbxy0Q__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)


Non-coding elements

![nce](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/gigascience/7/12/10.1093_gigascience_giy141/1/giy141fig4.jpeg?Expires=1617077560&Signature=g7EpAnYTp19n831k7ii8IKmseMOImee32PNighbMFBQRMumqhV6BBagOeGWOaFLsbqPf40UXFAZaCTWY9XLimRepBjYhfsOhgVwnEzVsf34QLb~BVBwSuaneQ2qV-t5EjuXm4YhXUVVFrdSz0J2YPa27z3P-Yd4iV-Mph1uonf~cGi~TVf7JHU4xLcq2nvgW8xT6rdj579mUKLdt~~PS-MOR78STZRC3Bx7IBSFFsX11thZcQxmjzm-h2bI2ze-j77FCYDvdjFrX9wj5rPMZhFpKBbW89u9qE0vhm7z2DbGoDg98mgerP6Lt8BuGG6rqV9BiPTLhQ9UAoTsTYu9I4w__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)

- #### [Draft genome sequence of Solanum aethiopicum provides insights into disease resistance, drought tolerance, and the evolution of the genome](https://academic.oup.com/gigascience/article/8/10/giz115/5579996)

- #### [The sequence and de novo assembly of Takifugu bimaculatus genome using PacBio and Hi-C technologies](https://www.nature.com/articles/s41597-019-0195-2#code-availability)

Divergence time estimation


![div](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41597-019-0195-2/MediaObjects/41597_2019_195_Fig4_HTML.png?as=webp)

Assembly pipeline

![asss](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41597-019-0195-2/MediaObjects/41597_2019_195_Fig1_HTML.png?as=webp)


- #### | De bonnes ref | 2020 | [Advances in optical mapping for genomic research](https://www.sciencedirect.com/science/article/pii/S2001037020303500#bi005)

[A near complete, chromosome-scale assembly of the black raspberry (Rubus occidentalis) genome](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6131213/pdf/giy094.pdf)

> NGS-based assemblies contain gaps in repetitive regions that exceed the maximum read lengths, and most genomes have thousands to millions of imbedded sequence gaps. These gaps can span biologically important sequences including tandem gene arrays, repeat dense, and haplotype- or homeologous-specific regions. Recent advances in single-molecule real-time (SMRT) sequencing have overcome the previous limitations of NGS-based approaches and ushered in a new era of “platinum-quality” reference genomes


- #### 2021 | PacBio Scientist | Diploid | Plant genome | Diploid | [A draft phased assembly of the diploid Cascade hop (Humulus lupulus) genome](https://acsess.onlinelibrary.wiley.com/doi/full/10.1002/tpg2.20072)


- #### [bowtie2](https://bioinformatics-core-shared-training.github.io/cruk-summer-school-2018/Introduction/SS_DB/Materials/Practicals/Practical2_alignment_SS.html)
- #### [Fast and accurate assembly of Nanopore reads via progressive error correction and adaptive read selection](https://www.biorxiv.org/content/10.1101/2020.02.01.930107v1.full)

- ### [Whole genome comparisons of Fragaria, Prunus and Malus reveal different modes of evolution between Rosaceous subfamilies](https://bmcgenomics.biomedcentral.com/track/pdf/10.1186/1471-2164-13-129.pdf)


- #### 2019 | [Genome sequence of Malania oleifera, a tree with great value for nervonic acid production](https://academic.oup.com/gigascience/article/8/1/giy146/5232231)

> De novo genome assembly and quality control

> First, primary assemblies (eight from PacBio long reads, one from 10× Genomics linked reads) were prepared by different pipelines. Next, scaffolding and polishing were performed on the optimal primary assemblies in order to obtain a final genome assembly. Primary assembly v0.1 was generated from PacBio long reads after correction by Canu v1.6 [19], assembly v0.2 by MECAT v1.1 [22], assembly v0.3 by miniasm v0.2-r168 [23] after alignment by minimap v0.2-r124 [23], assembly v0.4 by Falcon v0.7 (Falcon, RRID:SCR_016089) [24, 25] after correction with Canu v1.6, assembly v0.5 by SMARTdenovo v1.0.0 [26] after correction with Canu v1.6, assembly v0.6 by Wtdbg v1.2.8 [27] after correction with Canu v1.6, assembly v0.7 by SMARTdenovo v1.0.0 after correction, and assembly v0.8 by Wtdbg v1.2.8. Assembly v0.9 was prepared by Supernova assembler 2.0 [28, 29] from 10× Genomics linked reads data. Based on quality-control parameters, assembly v0.7 was chosen as optimal for further scaffolding and polishing. It generated a reasonably sized assembly (1.51 Gb), providing the highest N50 (i.e., the shortest sequence length at 50% of the total genome assembly length) (1.12 Mb) and the lowest number of contigs (3,038) and L50 (i.e., the smallest number of contig sequences whose lengths sum produces the N50 value) (330). Furthermore, genome assembly version v0.7 exhibited the longest contig length (6.72 Mb), as well as 71.80% gene completeness as determined by Benchmarking Universal Single-Copy Orthologs (BUSCO) (BUSCO, RRID:SCR_015008) [30] assessment (Supplementary Table S4). This assembly (v0.7) was further polished with raw PacBio long reads using arrow v2.2.1 [31] to produce (in two rounds) assembly v1.0. Subsequently, 10× Genomics linked reads were processed with Long Ranger [17, 18], and were then aligned to v1.0 using BWA mem v0.7.15 (default values, -t12) (BWA, RRID:SCR_010910) [32] and subsequently scaffolded by ARCS v1.0.1 [33] to produce assembly v1.1. The final assembly was generated after one further iteration of polishing with arrow v2.21 and three iterations with Pilon v1.22 (Pilon, RRID:SCR_014731) [34]. Before arrow-based polishing, PacBio raw reads were aligned using BLASR v5.1 (BLASR, RRID:SCR_000764) [35, 36], and PacBio raw reads were mapped with Bowtie2 v2.2.6 (Bowtie2, RRID:SCR_016368) [37] before each iteration with Pilon. In the final assembly, a genome size of 1.51 Gb was obtained, consisting of 2,987 contigs, 1,277 scaffolds (with contig N50 of 1.22 Mb, scaffold N50 of 4.65 Mb, longest contig of 6.7 Mb, and longest scaffold of 25.1 Mb), and with a gene completeness of 90.60% (Table 1 and Supplementary Table S4). The consistency of the predicted genome size based on k-mer characterization and the assembled genome indicated a good quality for our assembly. Furthermore, when all clean Illumina reads were mapped to the final assembly (v1.2f), a high sequence coverage of 98.5% was obtained. In addition, an even higher sequence coverage of 99.32% was observed for mapping PacBio long reads to the final assembly using BLASR. These two coverage values suggested high sequence completeness and fidelity of the genome assembly. Mapping rates (91%–98%) were also very high for transcriptomic datasets mapped to the final assembly, of which most (79%–96%) were uniquely mapped (Supplementary Table S1), with the exception of one RNA sequencing library (Short Read Archive accession: SRR7221534) that yielded low mapping rates (10.31%), a result that we cannot explain by anything aside from microbial or other contamination (see Supplementary File 1 for commands and settings).




> Metabolic gene clusters and candidate genes for fatty acid biosynthesis pathways
It is evident that genes for numerous plant secondary metabolic pathways are sometimes densely clustered in a specific genomic region, generating biosynthetic gene clusters (BGCs) [117–119]. With the newly released and robust computational toolkit, plantiSMASH [120], 23 such BGCs related to various secondary metabolic pathways were detected (Supplementary Table S21 and Supplementary File 4), such as saccharide- (10 gene clusters), terpene- (4), alkaloid- (2), polyketide- (1), and lignan-polyketide (1)-related. An additional five putative BGCs were identified that could not be assigned to specific secondary metabolic pathways. The identified BGCs spanned 258 to 1,282 Kb and contained three to eight core protein domains related to secondary metabolism.

> Given the importance of fatty acid production in M. oleifera, we further annotated genes within the fatty acid biosynthesis pathway by querying the Plant Metabolic Network (PMN v12.5, RRID:SCR_003778) [121, 122], after enzymatic annotations for coding genes through the E2P2 package v3.1 [123]. The initial (de novo) fatty acid biosynthesis process mainly occurs in plastids [124] of leaf mesophyll cells, seeds, and oil-accumulating fruits in plants. In this process, acetyl and malonyl groups are condensed and further elongated to give rise to the production of 16:0-ACPs (palmitic acids, acyl carrier protein) and 18:0-ACPs (stearic acid and oleic acids). After this initial process, very long-chain fatty acids (VLCFAs, with 22 or more carbons) can be synthesized at the endoplasmic reticulum by sequential addition of C2 moieties from malonyl-CoA to form C18 acyl groups [125].

> We detected 14 genes that are predicted to function in the four reactions of the elongation cycle, including the condensation of long-chain acyl-CoA and malonyl-CoA to form 3-oxoacyl-CoA, the reduction to 3-hydroxyacyl-CoA, the dehydration to (2E)-alkan-2-enoyl-CoA, and the final reduction to an elongated fatty acyl-CoA [125]. We detected 19 candidate genes potentially functioning in the reactions of the initial process (Supplementary Fig. S13) and 14 genes in the subsequent VLCFA biosynthesis pathway (Fig. 2c). Interestingly, we found the genes of the VLCFA pathway forming two gene clusters of local duplicates, one composed of four genes (Maole_016461, Maole_016463, Maole_016466, and Maole_016467) and the other of two genes (Maole_017397 and Maole_017398). These six genes occurring in localized clusters are all predicted to be involved in the four key reactions of the chain elongation cycle, suggesting an important effect of local gene duplication on efficient VLCFA production. By comparison, only a few cases (one including Maole_003221.T1 and Maole_003222.T1, the other including Maole_008716.T1 and Maole_008717.T1) of localized gene duplication were found for the initial fatty acid biosynthesis pathway.

























[Identification of genes associated with the biosynthesis of unsaturated fatty acid and oil accumulation in herbaceous peony ‘Hangshao’ (Paeonia lactiflora ‘Hangshao’) seeds based on transcriptome analysis](https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-020-07339-7)

[Sinbase 2.0: An Updated Database to Study Multi-Omics in Sesamum indicum](http://scholar.google.com/scholar_url?url=https://www.mdpi.com/2223-7747/10/2/272/pdf&hl=en&sa=X&d=17284092782916146238&ei=m4kdYOXkO4OBy9YPjse4yAk&scisig=AAGBfm2LhxAOmhx8SY-p6iRKKR2afwu3lg&nossl=1&oi=scholaralrt&hist=r6FjIyQAAAAJ:6622770154896122510:AAGBfm2NwlaOqR0GcREoxSGypHOL2nWX4w&html=)

[Insights into triterpene synthesis and unsaturated fatty-acid accumulation provided by chromosomal-level genome analysis of Akebia trifoliata subsp. australis](https://www.nature.com/articles/s41438-020-00458-y)


[Dr senthil](https://link.springer.com/article/10.1007/s11103-021-01122-2/figures/1)



- 01 February  Tecnology future | Nature methods | [Long road to long-read assembly](https://www.nature.com/articles/s41592-021-01057-y)



Non-dedicated hi-fi assembler is not appropriate

> Although noisy read assemblers can be applied to HiFi reads, he says they don’t take advantage of the high base-accuracy and won’t match HiCanu and hifiasm

Advantage of Hicanu and Hifiasm


> The assemblers HiCanu and hifiasm use string-overlap graphs to represent genomes, encode information for algorithmic analysis and show a reference and alternative paths along a DNA sequence, says Pevzner. The alternative paths represent variation at different loci. Graph genomes make it easier to resolve haplotypes. With string graphs, the nodes are reads and overlapping reads make up the edges, he says.




> Not many realize that hifiasm/HiCanu assemblies we produce today are of much higher quality than the assemblies we could get a year ago




> De burjin graph style not appropriate for long and accuate large k-mers "Li who"


 De Bruijn graphs are “the algorithmic engine” in assemblers such as SPAdes, Flye and wtdbg2, but they are not designed for making graphs with large k-mers



Polyploid assembly complexity

> “Then there are polyploid genomes and metagenomes, which are even harder to assemble,” he says. “These will keep us busy in the next five years at least.”



wtdbg2 and shasta versus hifiasm and Hicanu

> A major problem with wtdbg2, he says, is that it tends to collapse similar segmental duplications or repeats into one copy. “This results in an apparently smaller genome,” he says; the assembly is smaller than the ‘true’ genome. It’s a common issue with noisy read assemblers, says Li, but it’s more severe in wtdbg2 and Shasta. Hifiasm and HiCanu “don’t have this problem, which makes them better assemblers.”





Hifiasm faster than wtdbg2


> Hifiasm is faster than wtdbg2 because accurate reads can simplify most algorithms, Li says. Hifiasm can be used for haplotype-resolved assembly, but it’s applicable only to PacBio’s HiFi reads. He reckons the tool can be adapted for ultra-long ONT reads, “but this requires a lot of engineering work.”

According to Rhie hifiasm is goog for hapotig-resolved assembly


> In her view, hifiasm is likely to prove good for partitioning haplotypes.






reference free assembly assessment


> Even with more accurate reads, assemblies still need to be assessed for quality. For this task, she has co-developed Merqury8. The software can show what different assemblers are getting right and getting wrong, says Phillippy. Rhie says that parental k-mers can be used to validate haplotype phasing and that Merqury generates assembly assessment metrics with k-mers and does not use a reference. “Mapping biases” can trip up efforts to assess the quality of assemblies. For example, when evaluating an Asian assembled genome against the human reference, “any sort of Asian-specific variation would be called as an error,” she says. Especially in the genome’s repetitive regions, such bias can be more pronounced. “The k-mer-based approach sort of lifts away those mapping-based biases,” she says.








- 05 February 2021 | [Genetics of nodulation in Aeschynomene evenia uncovers mechanisms of the rhizobium–legume symbiosis](https://www.nature.com/articles/s41467-021-21094-7)





- #### [Whole-genome sequence diversity and association analysis of 198 soybean accessions in mini-core collections](https://academic.oup.com/dnaresearch/article/28/1/dsaa026/5974207)



- #### 2020 | OPINION [Polyploidy: A Biological Force From Cells to Ecosystems](https://www.cell.com/trends/cell-biology/fulltext/S0962-8924(20)30124-0)


- #### Blog [When the Growing Gets Tough, the Tough Get Pre-breeding](https://www.cwrdiversity.org/crop-science-special-issue-shows-why-crops-need-to-get-wild/)

- #### Blog [‘Crop Science’ special issue shows why crops need to get wild](https://news.globallandscapesforum.org/49393/crop-science-special-issue-shows-why-crops-need-to-get-wild/)











- #### LeafGo: Leaf to Genome, a quick workflow to produce high-quality De novo genomes with Third Generation Sequencing technology

[bIORIXV](https://www.biorxiv.org/content/10.1101/2021.01.25.428044v1.full.pdf)



GenomeScope 2.0 [36] was used to estimate, in silico, the genome sizes of both Eucalyptus species.





The software was run with the following parameters: 

```bash
[k-mer length=12, Ploidy=2, Max k-mer coverage=-1, average k-mer coverage for polyploid genome=-1].
```

We calculated the k-mer distribution,
which we then fed to GenomeScope, using JellyFish [51] with the following parameters: 

```bash

[jellyfish count -C -m 21 -s 1000000000].
```


To force Canu to keep haplotigs separate, we set the following parameters: 



```bash
batOptions=-dg 3 -db 3 -dr 1 -ca 500 -cp 50.

```




> We generated comprehensive assembly statistics using QUAST-LG v5.0.2 [55]. To assess the biological integrity of the assemblies, we used BUSCO v3 [56] as a proxy of genome completeness.










- #### Adam Phillipy team [publications](https://genomeinformatics.github.io/publications/)


- #### [examplewebdistill](https://bjungbogati.com.np/#skills) | create blog with distill [tuto1](http://uwesterr.de/posts/2020-01-17-create-a-blog-with-distill/) | [example design icon](https://databreadcrumbs.com/about.html) | [customization](https://themockup.blog/posts/2020-08-01-building-a-blog-with-distill/) | [themming](https://rstudio.github.io/distill/website.html?panelset1=inspiration&panelset3=screenshot3#custom-style)


- #### [Is It Ordered Correctly? Validating Genome Assemblies by Optical Mapping](http://www.plantcell.org/content/30/1/7)


- #### Efficient hybrid de novo assembly of human genomes with WENGAN | [paper](https://www.nature.com/articles/s41587-020-00747-w) [github](https://github.com/adigenova/wengan)

- #### example publication structural [variants](https://www.mdpi.com/2223-7747/9/4/523) by [Medhat Mahmoud](https://scholar.google.com/citations?hl=fr&user=hPJQuMgAAAAJ&view_op=list_works&sortby=pubdate) 


- ####  [example annotation pipeline](https://gigascience.biomedcentral.com/articles/10.1186/s13742-016-0134-5)

- #### [shasta installation](https://chanzuckerberg.github.io/shasta/QuickStart.html#QuickStartLinux)

- My mentor [Philipp Emanuel Bayer](https://scholar.google.com/citations?hl=ko&user=GOL15xQAAAAJ)

- Good for comparing Repeat and RNA set between two [plants](https://www.mdpi.com/1422-0067/21/1/3) | [good also](https://www.nature.com/articles/nature15714#Sec2)

- Good for polyploidazation and evolutionnary detection --->  [Building an octaploid genome and transcriptome of the medicinal plant Pogostemon cablin from Lamiales](https://www.nature.com/articles/sdata2018274)


- ####  Ten 10x Nanopore Bionano Hic | [Accurate assembly of the olive baboon (Papio anubis) genome using long-read and Hi-C data](https://academic.oup.com/gigascience/article/9/12/giaa134/6025063)
- #### The genome sequence of tetraploid sweet basil, ocimum basilicum L., provides tools for advanced genome editing and molecular breeding [DNA Research](https://academic.oup.com/dnaresearch/advance-article/doi/10.1093/dnares/dsaa027/6042144?login=true#supplementary-data)


- #### EXCLLENT INSPIRATION INDICUM GENOME | Good comparison example and graph with R | [Brassica napus](https://academic.oup.com/gigascience/article/9/12/giaa137/6034787) | [Cucumis sativus](https://academic.oup.com/gigascience/article/8/6/giz072/5520540?searchresult=1)



![img](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/gigascience/8/6/10.1093_gigascience_giz072/1/m_giz072fig2.jpeg?Expires=1623566636&Signature=Y940nOb~~a-vEOwUQKqJutqYVaWo~EJJxCs3Nauq1WgA4TR6K8nQgL7A9HE6plU0ejtMsjexKe19ztesQ6BD6Cly4fZzlQ7McfUStc4OI9cuWE-pF8QmgmcnER3hPeD822Qq-xoZocgUuKk8cXdxsiGe0GPEwPv5gK8oxCmV2U9xifa-UDk3hXKo7vPoAWIZra17CZDl-O4yfpnQyO3ilRaVWP8dgWSuAlGkLcUkqVjZZpL3qlouk7nYvE~8~bD3dl6Uo7QuejKC1e4EuxU0D5HUEEIdmqWxm716vSkH34uMwWt17iW2CC8tf~cFxWS7Sq~urRILE8E~7QI-hwSBzA__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)




- #### [Phased diploid genome assemblies and pan-genomes provide insights into the genetic history of apple domestication](https://www.nature.com/articles/s41588-020-00723-9)

- #### [Excellent tutot for full annotation and downstream analysis | Chromosomal genome of Triplophysa bleekeri provides insights into its evolution and environmental adaptation](https://academic.oup.com/gigascience/article/9/11/giaa132/5999722)





- #### [A reference high-density genetic map of Theobroma grandiflorum (Willd. ex Spreng) and QTL detection for resistance to witches’ broom disease (Moniliophthora perniciosa)](https://link.springer.com/article/10.1007/s11295-020-01479-3)




- #### [Phylogenomics resolves the invasion history of Acacia auriculiformis in Florida](https://onlinelibrary.wiley.com/doi/full/10.1111/jbi.14013)


- #### [Nice graph heterozigosity](https://www.frontiersin.org/articles/10.3389/fgene.2020.00440/full)


- #### [Guide writting short format](https://www.biorxiv.org/content/10.1101/2020.04.18.042093v1.full.pdf)

- #### [Awesome tutorial before wgs assembly](https://www.grandomics.com/en/complete_genome_survey/)

- #### [Awesome glance about de nov assembly and comparative genomics](https://www.grandomics.com/en/animal_and_plant_genome_de_novo/)

- #### [Grandomics genomics company pub](https://www.grandomics.com/en/pubications/)


- #### [Zoonomia project](https://www.nature.com/articles/s41586-020-2876-6) | [Code availability](https://www.nature.com/articles/s41586-020-2876-6#code-availability) 

- #### Gigascience Data Note Genome sequence | [Callicarpa americana](https://academic.oup.com/gigascience/article/9/9/giaa093/5902285) | [Potato](https://academic.oup.com/gigascience/article/9/9/giaa100/5910251#207670453) | [Aquilaria sinensis](https://academic.oup.com/gigascience/article/9/3/giaa013/5771296) | [Arachis monticola](https://academic.oup.com/gigascience/article/7/6/giy066/5040258) | [Eriobotrya japonica](https://academic.oup.com/gigascience/article/9/3/giaa015/5788433) |[Portunus trituberculatus](https://academic.oup.com/gigascience/article/9/1/giz161/5697200) | [catfish](https://academic.oup.com/gigascience/article/7/11/giy120/5106933) | [Juglans regia](https://academic.oup.com/gigascience/article/9/5/giaa050/5841058) |  [Juglans sigillata](https://academic.oup.com/gigascience/article/9/2/giaa006/5758190) | [mustache toad](https://academic.oup.com/gigascience/article/8/9/giz114/5572531) | [Prunus](https://academic.oup.com/gigascience/article/9/12/giaa130/6029397?searchresult=1)




- #### [Molecular Plant | Collection: Plant Genomics](https://www.cell.com/molecular-plant/collections/plant-genomics)

- #### [High-Resolution Genome-wide Association Study Identifies Genomic Regions and Candidate Genes for Important Agronomic Traits in Wheat](https://www.cell.com/molecular-plant/fulltext/S1674-2052(20)30221-5)  | GWAS | Population genomics

- #### [The Genomes of the Allohexaploid Echinochloa crus-galli and Its Progenitors Provide Insights into Polyploidization-Driven Adaptation](https://www.cell.com/molecular-plant/fulltext/S1674-2052(20)30214-8) | Tracking polyploidy 

- #### [The Chromosome-level Reference genome Assembly for Panax notoginseng and Insights into Ginsenoside Biosynthesis](https://www.cell.com/plant-communications/fulltext/S2590-3462(20)30144-9)

- #### [A Chromosome-Level Genome Assembly of Garlic (Allium sativum) Provides Insights into Genome Evolution and Allicin Biosynthesis](https://www.cell.com/molecular-plant/fulltext/S1674-2052(20)30232-X)

- #### [Deciphering the high‐quality genome sequence of coriander that causes controversial feelings](https://onlinelibrary.wiley.com/doi/full/10.1111/pbi.13310) | [Coriander Genomics Database: a genomic, transcriptomic, and metabolic database for coriander](https://www.nature.com/articles/s41438-020-0261-0)| MCMCTREE | DATABASE


- #### [The Chromosome-Level Genome Sequence of the Autotetraploid Alfalfa and Resequencing of Core Germplasms Provide Genomic Resources for Alfalfa Research](https://www.cell.com/molecular-plant/fulltext/S1674-2052(20)30216-1) | colinearity | MCscan | Ka Ks | Reseq | SNP | GATK

- #### [Development and evaluation of high‐density Axiom®CicerSNP Array for high‐resolution genetic mapping and breeding applications in chickpea](https://onlinelibrary.wiley.com/doi/full/10.1111/pbi.12836)

- #### [Toward the sequence-based breeding in legumes in the post-genome sequencing era](https://link.springer.com/article/10.1007/s00122-018-3252-x)

- #### [Integrating genomics for chickpea improvement: achievements and opportunities](https://link.springer.com/article/10.1007/s00122-020-03584-2)


- #### 07 September 2020 | Article | [Generation of a chromosome-scale genome assembly of the insect-repellent terpenoid-producing Lamiaceae species, Callicarpa americana](https://academic.oup.com/gigascience/article/9/9/giaa093/5902285)

- #### 28 August 2020 | Article | [The genome of the cauliflower coral Pocillopora verrucosa](https://academic.oup.com/gbe/advance-article/doi/10.1093/gbe/evaa184/5898631)

- #### 1 August 2020 | Article | [Chromosome-scale genome assembly of sweet cherry (Prunus avium L.) cv. Tieton obtained using long-read and Hi-C sequencing](https://www.nature.com/articles/s41438-020-00343-8)

- #### 8 May 2020 | Article | [Chromosome-level assembly of the horseshoe crab genome provides insights into its genome evolution](https://www.nature.com/articles/s41467-020-16180-1)
- #### 29 July 2020 | Article | [Gradual polyploid genome evolution revealed by pan-genomic analysis of Brachypodium hybridum and its diploid progenitors](https://www.nature.com/articles/s41467-020-17302-5)
- #### 1 August 2020 | Article | [A high-quality sponge gourd (Luffa cylindrica) genome](https://www.nature.com/articles/s41438-020-00350-9)
- #### 10 August 2020 | Article | [A high-contiguity Brassica nigra genome localizes active centromeres and defines the ancestral Brassica genome](https://www.nature.com/articles/s41477-020-0735-y#Sec4)
- #### 29th January 2020 | Article | [High quality 3C de novo assembly and annotation of a multidrug resistant ST-111 Pseudomonas aeruginosa genome: Benchmark of hybrid and non-hybrid assemblers](https://www.nature.com/articles/s41598-020-58319-6)
- #### 20 July 2020 | Review | [Plant pan-genomes are the new reference](https://www.nature.com/articles/s41477-020-0733-0)

- #### 01 October 2020 |Article | [From landrace to modern hybrid broccoli: the genomic and morphological domestication syndrome within a diverse B. oleracea collection](https://www.nature.com/articles/s41438-020-00375-0) | [Code available](https://github.com/zacharystansell/B_oleracea_diversity_panel)

- #### [Example linkgae map construction](https://www.mdpi.com/2223-7747/9/11/1476)

# Selection pressure analysis

- #### [Selection signatures of Fuzhong Buffalo based on whole-genome sequences](https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-020-07095-8)

# Root sesame

- #### Comparative Analysis of Root Transcriptome Profiles of Sesame (Sesamum indicum L.) in Response to Osmotic Stress](https://link.springer.com/article/10.1007/s00344-020-10230-0)


# Resequencing wild and cultivared

- #### [2021 | Whole-genome sequence diversity and association analysis of 198 soybean accessions in mini-core collections](https://watermark.silverchair.com/dsaa032.pdf?token=AQECAHi208BE49Ooan9kkhW_Ercy7Dm3ZL_9Cf3qfKAc485ysgAAAt4wggLaBgkqhkiG9w0BBwagggLLMIICxwIBADCCAsAGCSqGSIb3DQEHATAeBglghkgBZQMEAS4wEQQM2B_BJ-QzQ4xrW4A6AgEQgIICkS3885W8etg3s3QT-tEYzdWe9aH4FO1cwx33hHnc0OqJHxFRpVGCgOUfS10FIAmzQumt9Lq1TOm4o3bg0m9e-Gc1XLf22S5oFWPLESD4upL604-2sgz-WbDjP2rlHCjUNE3hrnFxh5ZLxFoFy4eM2tQux7eYm2rzi1y-fSwbyYCqkR-QQWzEP3bliNlyi8tmRdG-XFwKBu8VTCoY0cR9etz7BSZzqs8kM_0qUkShiq5QvAntkTwwJvIMJ3auUK9p9eChod12GDAu-HlOp73GY-ijoNJzTtUd4Kysb8KLokC7bcCI_vBQlxX8G4iHMqii5fJ8DVMjAH9BxAXO3H3betlafjUfsvS3hoiMHbKiw1eKh0ONWzl02wDOCO74Bq8GfsePJD3ywO-Sm-dDoy_xPRAW07aE80NbBcIY28o8QBXKRoD-WuSZeFfjSBWTjBgYDvrzyAbbwxZTxFjIRPovSUAse4zY94npm0oc5Ml52RuK7btKCpLBeL7Yi9Cx_Lopyu5jfw2T-ePfpJNwAY1h239Efw3KiVP_VpCGi-PVsJbQvjB_-ub6B2CHTkShU4lWaltKk78z7H-80LmVdkRHmBb9MrfKXj9oPKN1Bc7PKgdzJgxzPddUB2jX0aG1CGf22_Gyi-OeTa8mgSoHxw2ajLmfc-Rb7OL3zqpZ7rFIxAZjcwdZpeOu9ut6fIUbU_3IbvoXDRfLLTsZ9f-f5FJLPHJK-nxGFxZVkPK-5d5CNoOQ0Ep_NnU9QjBY-B2Gmr0_aDzK0CaSrOcUvjWdqeiKEdsaIev_L_bWTikaDoUhHbfzISNUwHWTIO_XGodEwb-_zY5_M7avw5Q4DXuuDa3vRvaVpdM6e3-Q6KaBdOFjG36r-w)

- ####  [2010 | Soybean 31](https://www.nature.com/articles/ng.715)
- ####  [2013 | Soybean | Korea](https://academic.oup.com/dnaresearch/article/21/2/153/403337)
- ####  [2015 | Soybean 302](https://www.nature.com/articles/nbt.3096)
- ####  [2014 | pepper](https://www.pnas.org/content/111/14/5135)
- ####  [2019 | Eggplant](https://www.frontiersin.org/articles/10.3389/fpls.2019.01220/full)
- ####  [2020 | Jujube](https://onlinelibrary.wiley.com/doi/10.1111/pbi.13480)
- ####  [2020 | Lotus](https://onlinelibrary.wiley.com/doi/abs/10.1111/tpj.15029)
- ####  [2020 | watermelon | 414](https://www.nature.com/articles/s41588-019-0518-4)
- ####  [2020 | Soybean](https://www.sciencedirect.com/science/article/pii/S0092867420306188?casa_token=v9ShlMGm3gQAAAAA:Sx5ybFWtapUYcU99V3aUWCsaaUWWqwvGmHlDdgud6q2yYWllCEV8oORQTueThOkpDgW09AAvoQ)
- ####  [2020 | Alfafa](https://www.sciencedirect.com/science/article/pii/S1674205220302161?casa_token=ocSWUtmqUeYAAAAA:ZUbB89_FygJ3F2EgClSg2EY6rVJD2A0HKAWVn9K9qtCSIEgBMoIZZSzv-CEX8Pu3jSX8HiSeJw)
- ####  [2020 | Tea | 81](https://www.sciencedirect.com/science/article/pii/S1674205220301349)
- ####  [2020 | Rice | 1143](https://www.nature.com/articles/s41467-020-18608-0)
- ####  [2020 | Common Bean | 683](https://www.nature.com/articles/s41588-019-0546-0)
- #### [2020 | Pepper | 4 | Italia](https://www.nature.com/articles/s41598-020-66053-2)



# Books

- #### [Computationnal genomics with R](https://compgenomr.github.io/book/)


# Snakemake


- #### [Install snakemake using conda](https://snakemake.readthedocs.io/en/stable/getting_started/installation.html)
- #### [Introduction to snakemake](https://blog.liang2.tw/2017Talk-Snakemake/#cover) | [A video](https://www.youtube.com/watch?v=aZ0QlqtR2KM)
- #### [Run snakemake locally](https://jrderuiter.github.io/snakemake-rnaseq/usage.html)
- #### [CulebrONT: Using data from long reads obtained by Oxford Nanopore Technologies sequencing makes genome assembly easier](https://culebront-pipeline.readthedocs.io/en/latest/)
- #### [VIPER: Visualization Pipeline for RNA-seq, a Snakemake workflow for efficient and complete RNA-seq analysis](https://bitbucket.org/cfce/viper/src/master/#RunningViper) 

- ##### [snakemake rna seq star deseq2](https://github.com/snakemake-workflows/rna-seq-star-deseq2)

- #### [RASflow: an RNA-Seq analysis workflow with Snakemake](https://github.com/zhxiaokang/RASflow)

- #### [Snake make Hista Strintie Deseq](https://github.com/KoesGroup/Snakemake_hisat-DESeq)

- #### [Variant calling example with snakemake](https://snakemake.readthedocs.io/en/v5.25.0/tutorial/basics.html)

- #### [snakemake-workflows dna-seq-gatk-variant-calling](https://github.com/snakemake-workflows/dna-seq-gatk-variant-calling/blob/master/Snakefile)






# Genomics Tools


- #### clustalo   running   `clustalo -t DNA --output-order=tree-order --outfmt=phylip --threads=8 -i CDS.final.fa -o CDS21.phylip`

- #### [Create an interactive dot plot from mummer output OR PAF format](https://github.com/tpoorten/dotPlotly/tree/master/example)


- ####  [auN: a new metric to measure assembly contiguity](https://lh3.github.io/2020/04/08/a-new-metric-on-assembly-contiguity)

- #### [Parliament2: Accurate structural variant calling at
scale](https://watermark.silverchair.com/giaa145.pdf?token=AQECAHi208BE49Ooan9kkhW_Ercy7Dm3ZL_9Cf3qfKAc485ysgAAAs8wggLLBgkqhkiG9w0BBwagggK8MIICuAIBADCCArEGCSqGSIb3DQEHATAeBglghkgBZQMEAS4wEQQMopDh_jGI9jtunPdUAgEQgIICgpCr6cFqmawIp2I0p0UXGnopbDiik5nBXScONWttNBw0wdZ94stvCH4MowuKdysZ5xa265Ti-qp9cXCfvkjb34w5_-KXG6rTW83B1sP8YnH_rUwOnfwZc9ateF6GukYjGVWZlYz1yWoCc_6yE8VmiIRCUaiocmZiwNl-AWI4qx5wYTJlMiv3LTRIw2-A5gig9kWZviQAhEPcdTdpeXkTK_vE-bX5y3dHGhzzkAyjTp7czgpdjRMHajbUFl5oPUB2skU-inGTNNcsLehDphCcRnfrMPYthAT8rK1tAX1mHBzb8VgFmYEaJC-pGRe70NbNKnLTEWiHn4l0x015RXubNj-S1oE7g7bMmQ4WRtoOcsh7rtaG6-4WpCEEl8UJnVyLTceWpHlg_F1_BgUq7_qno_fI_nwCRFaHPqxRIydgh3knNyERHMMkJoMWP8J0Xiixw2YTekBMH38JgNtRSj0tEvyxmaM-XZIMlLfbjCIP6Q2hcnIjX7QzNiJP35fsukllFCt2PxqkSWlJyHjTzu1-vGG0olCT-eDZSvwGTwG7OZ_N2Ysi3f4qGeUhRfV2sBhgS0NFm7eedl3hQpKPV9toPX_9zopR8Kpo6dvwD5azqjB9TzhWazJOEJAL8oi1SaeK1d-cHiJrKSRRpoRWM7vj6CBAa-ns8eBN2U7rpLFfsOqs1XKiLCBB8EAZHycGky47VacivVC1DC7s4bBg4QJJEtA69xM9YoroUxC9SM-Fcz5Vdgs3PSDsU2aCMs_v2Wjlnf48_SJ8pJ1iKm79tPwFk5ja7GyG9DNSFK4XQQolXhywQFBKWPvrKTLI874g_k2nYwRQVNQUuJJM54AjwBABV_gfcA)


- #### Wonderfull tool for plastid representation [website](https://irscope.shinyapps.io/Chloroplot/) | [paper](https://www.readcube.com/articles/10.3389/fgene.2020.576124)

- #### [LongQC: A Quality Control Tool for Third Generation Sequencing Long Read Data](https://www.g3journal.org/content/ggg/10/4/1193.full.pdf)
- #### [D-GENIES – for Dot plot large Genomes in an Interactive, Efficient and Simple way – is an online tool designed to compare two genomes. It supports large genome and you can interact with the dot plot to improve the visualisation.](http://dgenies.toulouse.inra.fr/)

- #### [Genome Assembly with Minimap2 and Miniasm with pacbio data](https://github.com/lh3/miniasm)
- #### [Genome Assembly with Minimap2 and Miniasm with nanopore data](https://timkahlke.github.io/LongRead_tutorials/ASS_M.html)

- #### [Nanopore explanation reads trimming and so on:  Telomere length de novo assembly of all 7 chromosomes and mitogenome
sequencing of the model entomopathogenic fungus, Metarhizium brunneum,
by means of a novel assembly pipeline
](https://assets.researchsquare.com/files/rs-60098/v2/e4035f37-970c-481e-8d23-05b18f9783b6.pdf)

- #### [IJV Tool](https://wikis.utexas.edu/display/bioiteam/Integrative+Genomics+Viewer+%28IGV%29+tutorial)

- #### [Assembly Graph Browser: interactive visualization of assembly graphs](https://pubmed.ncbi.nlm.nih.gov/30715194/)

- #### [Visualising Assembly Graphs](https://towardsdatascience.com/visualising-assembly-graphs-fb631f46bbd1)

- #### [Excellent tutorials for long reads assembly and so on](https://yiweiniu.github.io/blog/)
- #### [Accessing data from NCBI with EDirect](https://astrobiomike.github.io/unix/ncbi_eutils)

- #### [Webinar: GWA of a wheat transcription factor family: the power of bioinformatics resources](https://youtu.be/efbph7f2jXU)

- #### [Hi-fi assembly yutorial](https://youtu.be/5tE8zYDpC8c)

- #### [Long reads assembly tutorial with a focus on nanopore data](https://timkahlke.github.io/LongRead_tutorials/ASS.html)
- #### [How to read a phylogenetic tree](https://youtu.be/LgZ3UbPzC6c)

- #### [Submitting a haploid assembly: submitting WGS contigs only](https://www.ncbi.nlm.nih.gov/assembly/docs/submission/#ex1)

- #### [Genome colinearity analysis tool: MCScan](https://github.com/tanghaibao/mcscan)
- #### [Genome colinearity analysis tool: MCScanX](https://github.com/wyp1125/MCScanX)
- #### [Genome colinearity visualization tool Synvisio](https://github.com/kiranbandi/synvisio)

- #### [Shark: fishing relevant reads in an RNA-Seq sample](https://doi.org/10.1093/bioinformatics/btaa779)
- #### [TBtools](https://github.com/CJ-Chen/TBtools) | [Paper](https://www.sciencedirect.com/science/article/pii/S1674205220301878)
- #### [Ka ks calculation with TBtools](https://www.youtube.com/watch?v=-KjSdr-hmk4)
- #### [Exon-intron identification](https://www.youtube.com/watch?v=60V0WscNEQE)
- #### [Syntheny analysis in TBtools](https://www.youtube.com/watch?v=v-t0z0UrHqQ)
- #### [ka ks online](http://services.cbu.uib.no/tools/kaks)
- #### [Best Practices/Softwares To Calculate Ka/Ks Ratio](https://www.biostars.org/p/5817/)
- #### [Bayesian Molecular Clock Dating Using Genome-Scale Datasets](https://link.springer.com/protocol/10.1007/978-1-4939-9074-0_10)
- #### [MCMCtreeR: functions to prepare MCMCtree analyses and visualize posterior ages on trees](https://academic.oup.com/bioinformatics/article-abstract/35/24/5321/5530964?redirectedFrom=fulltext)  |  [MCMtreeR](https://cran.r-project.org/web/packages/MCMCtreeR/vignettes/MCMCtree_plot.html)  | [MCMtreeR vignette](https://cran.r-project.org/web/packages/MCMCtreeR/vignettes/MCMCtree.html)



- #### RepeatModeler instalation 

[official](https://github.com/Dfam-consortium/RepeatModeler)

[1 blog](http://kazumaxneo.hatenablog.com/entry/2020/07/03/073000) | [2 official](http://www.repeatmasker.org/RepeatModeler/) | [3 incodom](http://www.incodom.kr/RepeatModeler)  | [4 docker](https://hub.docker.com/r/pakorhon/repeatmodeler)  | [5 installation guide](http://www.hpc.lsu.edu/docs/faq/installation-details.php)  | [6](https://taoyan.netlify.app/post/2020-03-02.edta-%E8%BD%AC%E5%BA%A7%E5%AD%90%E6%B3%A8%E9%87%8A/)   | [7](https://www.jianshu.com/p/a8c9e875b17f)  |  [8](https://www.douban.com/note/777662891/)   |  [9](https://www.programmersought.com/article/25101639140/)  |  



[un site par haserd tutorial interessant](http://www.wuchangsong.com/?cat=4)

[edta](https://blog.csdn.net/u012110870/article/details/103903879)


[astuce](https://www.qdxingtu.com/key/Error%20running%20repeatModeler.html)


```

astuce... 

The only thing that worked for me was to install all dependencies in a conda environment and installing RepeatModeler 2.0.1 and RepeatMasker 4.1.0 downloaded from GitHub separately (not with conda) and linking all dependencies of the two configure scripts to the conda environment.
```




# Singularity

[1](https://www.sdsc.edu/education_and_training/tutorials1/singularity_old.html)



# Genomics

- #### [Heng Li blog](https://lh3.github.io/2020/12/25/evaluating-assembly-quality-with-asmgene)

- #### NBIS `National Bioinformatics Infrastructure Sweden` Genome assembly Tuto  [schedule](https://nbisweden.github.io/workshop-genome_assembly/schedule) | [1](https://nbisweden.github.io/workshop-genome_assembly/exercises/exercise_1.html) | [2](https://nbisweden.github.io/workshop-genome_assembly/exercises/exercise_2.html) | [3](https://nbisweden.github.io/workshop-genome_assembly/exercises/exercise_3.html) | [4](https://nbisweden.github.io/workshop-genome_assembly/exercises/exercise_4.html) | [6](https://nbisweden.github.io/workshop-genome_assembly/exercises/exercise_6.html) | [7](https://nbisweden.github.io/workshop-genome_assembly/exercises/exercise_7.html) | [8](https://nbisweden.github.io/workshop-genome_assembly/exercises/exercise_8.html) | [9](https://nbisweden.github.io/workshop-genome_assembly/exercises/exercise_9.html) | [10](https://nbisweden.github.io/workshop-genome_assembly/exercises/exercise_10.html) | 

- ####  [Inspirational graph for genome assembly evaluation](https://www.biorxiv.org/content/10.1101/715722v1.full.pdf)


- #### [GenomeQC](https://github.com/HuffordLab/GenomeQC) | [Docker available]
- #### [Assembly NGx plot](https://link.springer.com/article/10.1186/s12864-020-6568-2/figures/3)

- #### [tutorial phylogeny](http://www.metagenomics.wiki/tools/phylogenetic-tree/construction)   [tuto](http://www.metagenomics.wiki/tools/phylogenetic-tree/alignment)

- #### [great example of comparative genomics of plants ...tu dois suive cet example pour sesamum alatum prevu pour gigascience  Usage de orthofinder avec option blast....phylogenetic and divergence time estimation wonderfull tutorial](https://www.frontiersin.org/articles/10.3389/fgene.2019.01211/full)

- #### [Great inspiration Murigneux Valentine](https://www.biorxiv.org/content/10.1101/2020.03.16.992933v1) | [Video](https://youtu.be/FuyMgjROOIk)

- #### [Code genome kiwifruit](https://www.protocols.io/view/chromosome-scale-genome-assembly-of-kiwifruit-acti-vgse3we)

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



- #### [funannotate](https://github.com/nextgenusfs/funannotate)
- #### [Fungap](https://github.com/CompSynBioLab-KoreaUniv/FunGAP)

- #### [annotation tools](https://github.com/NBISweden/GAAS/blob/master/annotation/knowledge/annotation_tools_genome.md)


- #### [Maker run tutorial by Daren Card](https://gist.github.com/darencard/bb1001ac1532dd4225b030cf0cd61ce2)

- #### [Maker Pipeline [2011 - v2.31.10 (May 4, 2018)](https://m.blog.naver.com/PostView.nhn?blogId=naturelove87&logNo=221491035712&proxyReferer=https:%2F%2Fwww.google.com%2F) | [MAKER](http://www.incodom.kr/MAKER) | [Methods](https://bioinformaticaupf.crg.eu/20132014/projectes1314/1C/Materials_and_methods.html)

- #### [Tuto for Tuxedo pipeline 1](https://colauttilab.github.io/NGS/TuxedoTutorial.html)

- ####  [Tuto for Tuxedo pipeline](https://github.com/trinityrnaseq/RNASeq_Trinity_Tuxedo_Workshop/wiki/Tuxedo-Genome-Guided-Transcriptome-Assembly-Workshop)

- ### [good tuto for deseq code and edger code](https://github.com/Yedomon/RNA-seq-tutorial-for-gene-differential-expression-analysis)

- #### [good tuto DESEQ](https://genviz.org/module-04-expression/0004/02/01/DifferentialExpression/)

- #### [Genomic Data Visualization and Interpretation](https://genviz.org/course/)

- #### [Excellent paper on RNA DEG spipeline](https://www.nature.com/articles/s41598-019-43421-1#Sec9)

- #### Deseq tuto [1](http://evomics.org/wp-content/uploads/2018/10/RNASeqWorkFlow-1.html) [2](https://rpubs.com/otienolwanga/problem_solving) [3](https://rpubs.com/mwken314/deseq2)

- #### HISAT2 HTseq DeSeq2 Rna tuto [1](http://www.cbs.dtu.dk/courses/27626/Exercises/rnaseq.php) | [2](https://pzweuj.github.io/2018/07/12/rna-seq-3.html) | [3 Hisat2 and featcount](https://bioinformaticsworkbook.org/dataAnalysis/RNA-Seq/RNA-SeqIntro/RNAseq-using-a-genome.html#gsc.tab=0) and [Deseq2](https://bioinformaticsworkbook.org/dataAnalysis/RNA-Seq/RNA-SeqIntro/Differential-Expression-Analysis.html#gsc.tab=0)


- #### [featureCounts and important note for aligner relative to short reads] (https://hbctraining.github.io/Intro-to-rnaseq-hpc-O2/lessons/05_counting_reads.html)

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





# R spatial

- #### [ggplot2 dataviz r map github](https://github.com/sergiocostafh/ggplot2_dataviz)
- #### [R Maps: Beautiful Interactive Choropleth & Scatter Maps with Plotly](https://youtu.be/RrtqBYLf404)
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

# Sesamum alatum

- #### [Inspirationnal paper 1](https://www.sciencedirect.com/science/article/pii/S0888754318306591)


# Cucumis 


- #### [Syntenic relationships between cucumber (Cucumis sativus L.) and melon (C. melo L.) chromosomes as revealed by comparative genetic mapping](https://bmcgenomics.biomedcentral.com/articles/10.1186/1471-2164-12-396)
- #### [Cucumber (Cucumis sativus) and melon (C. melo) have numerous wild relatives in Asia and Australia, and the sister species of melon is from Australia](https://www.pnas.org/content/107/32/14269)
- #### [Pumpkins, cucumbers, and watermelons diverged from a single melon ancestor](https://geneticliteracyproject.org/2017/10/13/pumpkins-cucumbers-watermelons-diverged-single-melon-ancestor-study-shows/)
- #### [RELATIONSHIPS OF CUCUMBERS AND MELONS UNRAVELED:MOLECULAR PHYLOGENETICS OF CUCUMIS AND RELATED GENERA (BENINCASEAE, CUCURBITACEAE)](https://bsapubs.onlinelibrary.wiley.com/doi/pdfdirect/10.3732/ajb.94.7.1256)
- #### [Comparative Analysis between Wild and Cultivated Cucumbers Reveals Transcriptional Changes during Domestication Process](https://www.mdpi.com/2223-7747/9/1/63/htm)
- #### [QTL mapping and genome-wide association study reveal two novel loci associated with green flesh color in cucumber](https://link.springer.com/article/10.1186/s12870-019-1835-6)




# NNS-LRR genes 

- #### [Inspirational paper 1](https://bmcplantbiol.biomedcentral.com/articles/10.1186/s12870-020-02576-0#Sec16)
- #### [Dioscorea](https://www.frontiersin.org/articles/10.3389/fgene.2020.00484/full)
- #### [Cassava](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4422547/pdf/12864_2015_Article_1554.pdf)
- #### [Inspirational paper 2](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0239275)



# Linkage mapping

- #### [High-density linkage map reveals QTL for Type-I seed coat cracking in RIL population of soybean [Glycine max (L.) Merr.]](https://link.springer.com/article/10.1007/s10681-020-02684-w)

# Genetic diversity

- #### [Diversity analysis of 80,000 wheat accessions reveals consequences and opportunities of selection footprints](https://www.nature.com/articles/s41467-020-18404-w) | [Code github](https://github.com/jfranco1951/Genetic-Diversity)


# Dotplot RNA

- #### [ Dotplot RNA](https://www.biostars.org/p/327039/)




# Doudou Sylla

#### [graph 1](https://www.google.com/search?q=GGPLOT2+FACET&rlz=1C1EJFC_enKR900KR900&sxsrf=ALeKk03R6Jk9D47FDaWh9PPny2tn9Nu_MQ:1600266205845&source=lnms&tbm=isch&sa=X&ved=2ahUKEwj99PqV8O3rAhWRMd4KHVIqAkQQ_AUoAXoECA4QAw&biw=1920&bih=920#imgrc=5k-afjZeAPxLkM&imgdii=kWtsYbSNy82DSM) | [barplot](http://www.sthda.com/french/wiki/ggplot2-barplots-guide-de-demarrage-rapide-logiciel-r-et-visualisation-de-donnees) | [cord_flip](http://www.sthda.com/french/wiki/ggplot2-barplots-guide-de-demarrage-rapide-logiciel-r-et-visualisation-de-donnees) | [faceting](https://www.r-graph-gallery.com/223-faceting-with-ggplot2.html)  | [example](https://stackoverflow.com/questions/34001024/ggplot-order-bars-in-faceted-bar-chart-per-facet)



#### Tuto colinearity [MCScanX](https://github.com/wyp1125/MCScanX)


##### Step 1:  Create a m8 format BLASTP file

I assume I have Arabidopsis and xyz plant genome for colinearity work

So, I should make a database for 

First, we need to tell BLAST that the Arabidopsis sequences are (a) a database, and (b) a protein database. That’s done by calling ‘makeblastdb’:

```
makeblastdb -in Ara.protein.faa -dbtype prot

```

then run blastall


```

$blastall  -i  myxyz_query_file_protein.fasta  -d Ara.protein_database -p blastp -e 1e-10 -b 5 -v 5 -m 8 -o xyz.blast


```


For MSCsanX  you should have an output lin m8 [format](https://edwards.sdsu.edu/research/blast-output-8/). An example [here](https://raw.githubusercontent.com/wyp1125/MCScanX/master/data/at.blast)


```

AT1G50920   AT1G50920    100.00  671     0       0       1       671     1       671     0.0     1316

```


Make sure you have this format before downstream analysis



## Step 2: Create a simplified "gff" file as inputs

I need to install bedops in order to parse the gff files. [A biostar resource for this operation](https://www.biostars.org/p/61386/)

I will use conda since I do not have a rot access.

I will set a specific environment.


```

conda create -n bedops_env


```

Then activate the environment

```
source activate bedops_env

```

Then install the tool

```

conda install -c bioconda bedops


```

Now use the tool to parse my gff file. A nice help is [here](https://bedops.readthedocs.io/en/latest/content/reference/file-management/sorting/sort-bed.html)


```

sortBed -i myfile.gff | gff2bed > my_sorted_file.bed

```

The xyz.bed file holds gene positions, following a tab-delimited format like [this](https://github.com/wyp1125/MCScanX/blob/master/data/at.gff):


```
chr#    starting_position       ending_position gene

```

Note: for chr#, a two-letter short name is used as prefix for the species; # is the chromosome number. (For example, the second chromosome of Arabidopsis thaliana should be denoted as at2.) The bed format is defined here, and is especially useful since there are a ton of tools that can handle bed files, most notably BEDTOOLS. The xyz.bed file can be generated by parsing the .gff3 file released by the sequencing initiatives. Repeat of the same gene is not allowed in the .bed file. When comparing multiple genomes, simply concatenate all inter-/intra-species m8 blast output into xyz .blast file and concatenate all gene positions of different species into xyz.bed file.

It is advised that to make MCscanX generate more reasonable results, the number of BLASTP hits for a gene should be restricted to around top 5. When you have xyz.blast and xyz.bed ready, put them in the same folder. Then you can simply use:

```

$ ./MCScanx  dir/xyz

```

[here](https://youtu.be/KMlj8CGnB2c?t=477) a video on how to run it.



possible to calculate ka ks with bioperl with the .syntheny output of MCscan. follo this [tuto](possible to calculate ka ks with bioperl with the .syntheny output of MCscan 
)

#### Note

A guy I know use a four step logic

- Step1: get coliniarity gene wih MCScanX(https://github.com/wyp1125/MCScanX)

- step2: Multiple sequence alignement of those colinear genes with ClustalW2

- step3: Convert into codon WITH [pal2nal](http://www.bork.embl.de/pal2nal/) | [pal2nal](https://figshare.com/articles/An_example_of_PAL2NAL_input_and_output_files/9192)

- step4: calculate ka ks with CODEML of [PAML](https://www.protocols.io/view/introduction-to-calculating-dn-ds-ratios-with-code-qhwdt7e) | [EasyCodeML: A visual tool for analysis of selection using CodeML](https://onlinelibrary.wiley.com/doi/full/10.1002/ece3.5015)  | [github](https://github.com/BioEasy/EasyCodeML)  | [download](https://github.com/BioEasy/EasyCodeML/releases/tag/1.0)

- step5: plot the density graph in R WITH GGPLOT2

#### TIME DIVERGENCE



Here a [resource](http://www.timetree.org/resources).


My guy use Reltime estination methode with MEGA  after Single copy alignment with MAFFT

He download some calibration files on timetree.org and run I think

a good tuto for RELTIME time divergence estimation with [MEGAx](https://www.megasoftware.net/pdfs/mello_2018.pdf)

for the calibration he retieve from timetrre.org database 



[a nice and complete tutorial video](https://www.youtube.com/watch?v=x5TqC5okZWo)

[Inferring selection with MEGA](https://www.youtube.com/watch?v=wNLZoKkdJ38)


un nice tuto sur cette affaire de time tree et autre [ici](https://kor.kyhistotechs.com/complex-jujube-genome-provides-insights-into-fruit-tree-biology-31050929)


#### Visualize syntheny


Now I want to visualize the syntheny. 

[Synvisio is awesome](https://github.com/kiranbandi/synvisio)

I just need two files:

- The simplified gff file that was used as an input for a McScanX query.
- The collinearity file generated as an output by McScanX for the same input query.


Possible to do that [online](https://synvisio.github.io/#/)



in case of troubles for making bed file please Yedomon go to this [page](https://github.com/tanghaibao/jcvi/wiki/MCscan-%28Python-version%29#workflow)

Instal jcvi [conda package manager](https://anaconda.org/bioconda/jcvi) 

and follow [this plan](https://github.com/tanghaibao/jcvi/wiki/MCscan-%28Python-version%29#workflow)

jvci is a python version of MCScan ..so you can use it also. And jvci can help you to render nice visualization  




I just discover a very nice and helpfull website for some [sofwares](https://sites.google.com/view/dr-wasim/softwares) , [protocol](https://sites.google.com/view/dr-wasim/protocols/nucleic-acid-extraction) , [tutorials](https://sites.google.com/view/dr-wasim/bioinformatic-tools/tbtools)

# Whole genome duplication



[nice paper](https://www.nature.com/articles/s41467-020-18771-4)

Can be proved through ka?ks analysis graph, syntheny graph, phylogenetic tree time divergence analysis... Example with this [paper](https://onlinelibrary.wiley.com/doi/full/10.1111/1755-0998.13261#men13261-fig-0003) and this [paper](https://onlinelibrary.wiley.com/doi/full/10.1111/pbi.13350)

[Good review](https://www.cell.com/trends/plant-science/fulltext/S1360-1385(18)30159-6)




[How to parse orthofinder results?](https://www.biostars.org/p/366002/)



#### How to download genome data from ncbi

I wanted to download bacteria genome assembly from ncbi, but I did not know how to do.

By googling I fortunately found this [link](https://www.ncbi.nlm.nih.gov/datasets/docs/command-line-assembly/)

They recommand to install the ncbi program named datasets. How to install it ? The response is [here](https://www.ncbi.nlm.nih.gov/datasets/docs/rehydrate/).

It is possible to downmload a hude dataset from a taxon with NCBI taxon ID. 

After installation type ./datasets download genome taxon --help to see the details arguments

an other way to do is to [here](https://astrobiomike.github.io/unix/ncbi_eutils) and [here](https://dmnfarrell.github.io/bioinformatics/assemblies-genbank-python)



#### SP work

- #### [Inspiration 1](https://peerj.com/articles/9448/)

- #### [Inspiration 2](https://link.springer.com/article/10.1007/s13205-020-02372-5)

#### Population genomics work 

##### Sesame

- #### [Cui et al 2017](https://www.frontiersin.org/articles/10.3389/fpls.2017.01189/full)
- #### [Mei et al 2017](https://www.frontiersin.org/articles/10.3389/fpls.2017.00636/full)

##### Others
- #### [Perfect example](https://www.cell.com/molecular-plant/fulltext/S1674-2052(18)30343-5)
- #### [Jujube example](https://onlinelibrary.wiley.com/doi/10.1111/pbi.13480)
- #### [Wheat](https://link.springer.com/article/10.1186/s12864-020-06835-0#Sec14)
- #### [Joukhadar et al 2017](https://www.frontiersin.org/articles/10.3389/fpls.2017.02115/full#h3)
- #### [Wang et al 2018](https://www.cell.com/molecular-plant/fulltext/S1674-2052(18)30187-4#secsectitle0020) | Domestication area
- #### [Good journal for publication](https://gsejournal.biomedcentral.com/articles/10.1186/s12711-020-00581-3#Sec2)

# Homework seed science

The idea is to use wild genome for rice sedd nutritionnal quality improvmen through genomics breeding

Some references

- #### [Potentiality of Wild Rice in Quality Improvement of Cultivated Rice Varieties](https://link.springer.com/chapter/10.1007/978-981-15-4120-9_4)

- #### [Germplasm and Genetic Diversity Studies in Rice for Stress Response and Quality Traits](https://link.springer.com/chapter/10.1007/978-981-15-4120-9_3)
- #### [Rice Grain Quality and Abiotic Stress: Genomics and Biotechnological Perspectives](https://link.springer.com/chapter/10.1007/978-981-15-4120-9_30)
- #### [argument important of reseq for agronomic traits](https://link.springer.com/chapter/10.1007/978-981-15-4120-9_6)

- #### [genome wild rufipogon](https://www.nature.com/articles/s42003-020-0890-8#Sec8) | [another version](https://link.springer.com/article/10.1007/s11427-020-1738-x)
- #### [proteomics analysis](https://link.springer.com/article/10.1186/s12953-014-0051-4)
- #### [Improvement of Nutritional Quality of Rice Seed Through Classical Breeding and Advance Genetic Engineering](https://link.springer.com/chapter/10.1007/978-981-15-5337-0_23)
- #### [nICE GRAPH R ](https://nph.onlinelibrary.wiley.com/doi/full/10.1002/ppp3.10151)
# Karyotyping paper

- #### [High impact factor potential journal: Journal of Genetics and Genomics](https://www.journals.elsevier.com/journal-of-genetics-and-genomics)
- #### [Example IF = 6.141 ](https://onlinelibrary.wiley.com/doi/full/10.1111/tpj.14536)
- #### [Example IF = 2.076](https://academic.oup.com/botlinnean)
- #### [Example 2020 Frontiers in Plant Science IF = 4.402](https://www.frontiersin.org/articles/10.3389/fpls.2020.00569/full)
- #### [Example 0: IF = 5.065 | Construction and application of oligo-based FISH karyotype of Haynaldia villosa](https://www.sciencedirect.com/science/article/pii/S1673852718301164)
- #### [Example 1: IF = 3.395 | The Crop Journal ](https://www.sciencedirect.com/science/article/pii/S2214514116300484)
- #### [Example 2: IF = 1.085 | Biochemical Systematics and Ecology](https://www.sciencedirect.com/science/article/pii/S0305197815002203)
- #### [Example 2: IF = 1.662 | Frontiers in Life Science](https://www.tandfonline.com/doi/full/10.1080/21553769.2015.1041166)
- #### [Example 3: IF = NA | Plant Breed. Biotech.](http://www.plantbreedbio.org/journal/view.html?volume=7&number=3&spage=237&year=2019)

# Download nt and nr from ncbi

[solution](https://www.biostars.org/p/387902/)


# Review : Understanding African plant diversification: insights from special plant species complexes in sub-Saharan Africa


- #### [Cradles and museums of generic plant diversity across tropical Africa](https://nph.onlinelibrary.wiley.com/doi/full/10.1111/nph.16293#nph16293-bib-0016)

- #### [Beyond trees: Biogeographical regionalization of tropicalAfrica](https://onlinelibrary.wiley.com/doi/pdf/10.1111/jbi.13190?casa_token=4NHZao-oL4cAAAAA:AXDZLPyk6aNkZl2PnqV1Fq7tKXYot7wYp5LS0hZOQvRWauK5_zf1ceSOMEUpSJOEmQH4X_3YK7e2YTj8)


- #### [PLANT SYSTEMATICS IN SOUTH AFRICA: A BRIEF HISTORICAL OVERVIEW, 1753–1953](https://www.tandfonline.com/doi/abs/10.1080/00359199909520411?journalCode=ttrs20)

- #### [Floristics of the angiosperm flora of Sub-Saharan Africa: an analysis of the African Plant Checklist and Database](https://www.researchgate.net/publication/233681713_Floristics_of_the_angiosperm_flora_of_Sub-Saharan_Africa_an_analysis_of_the_African_Plant_Checklist_and_Database)


# Earlier African systematics investigation

The African continent is composed of more than 45,000 species distributed on a area of 29 million km2 (Klopper, R. R., Gautier, L., Chatelain, C., Smith, G. F., and Spichiger, R. (2007). Floristics of the angiosperm flora of sub-Saharan Africa: an analysis of the African plant checklist and database. Taxon 56, 201–208.). Early 1600's, diverse European botanists started the documentation of African flora. Individual investigations based on diverses schools dependending on the practitionners were used. However, the traceability of the collected data and the lack of communication make difficulta comprehensive knowledge of the African plants classification. Plant systematics in Africa has evolved a dramatic turn with the Association pour l'Etude Taxonomique de la Flore d'Afrique Tropicale (AETFAT) (Association for the taxonomic study of the flora of tropical Africa in English).





# How I solved ALI TV installation in my Centos 7


```
sudo yum install perl-devel

sudo yum install cpanminus

sudo cpanm Bio::Perl # to install bioperl tools

sudo cpanm --force Bio::Perl # force failed installation module

```



I got the solution [here](https://www.biostars.org/p/345331/)

to visualize  ...... https://alitvteam.github.io/AliTV/d3/AliTV.html


awesome tuto [here](https://alitvteam.github.io/AliTV/gcb_2016)


# Nucmer alignement artemis

Hi Yedomon,

 

Below is the command for nucmer, delta-filter, show-coords, comparison file. I hope you can make it. 

 

the lines not started with # are the command you will use. 

#Let's suppose you have a delta file called "gb_zz.delta", which was produced by nucmer with ref=zz, query=gb.

#Do show-coords with -cTrl option like below;

show-coords -cTrl gb_zz.delta > gb_zz.delta.coords

#or do delta-filter first with %match (-i option) >=95% and match length (-l option) >=500bp

delta-filter -i 95 -l 500 gb_zz.delta > gb_zz_i95l0.5k.delta

#then do show-coords like above.
#Now let's make a comparison file for ACT like below;

more gb_zz.delta.coords | awk '$0~/^[0-9]/' | awk '{print $5,$7,$1,$2,$12,$3,$4,$13}' > gb_zz.cmp

=====below is not a commend
#where each column has;
$5=alignment_len of reference
$7=%id
$1,$2,$12=ref start, end, Ref_name (always +)
$3,$4,$13=qry start, end, Qry_name (can be +/-)

#load gb_zz.cmp file to ACT
sequence1=reference
sequence2=query
comparison_file=gb_zz.cmp


 

Let me know if you have any problem. Good luck.

 

Yeisoo


One day I face a problem ....when running a well install programm under linux.


The problem was slove using the command: 


chown -R user:user folder/


Permission issue was the problem

# Trover un moyen de gerer les gaps surtout leur positions dans une sequence

-Une reponse [ici](https://stackoverflow.com/questions/49303791/finding-the-positions-and-lengths-of-gaps-indels-in-a-sequence-alignment-with) que je peux adapter a mon cas en remplacant le - par N

 comme par hasard je decouvre ceci..comment visualiser la proportion de gap dans un genome. tres interessant. site [ici](https://bioinformaticsworkbook.org/dataWrangling/R/visualize-gaps-in-genomes.html#gsc.tab=0)
 
 
 
 ### Pour record ram max installer yime em faisant yum install time puis lancer votre code comme ceci /usr/bin/time -o out.time.ram.txt -v votrecommande &> log & 
 
 
 # Back-to-back bar graph 
 
 - #### [video](https://www.youtube.com/watch?v=DbFU7Js8_h4)
 
 - #### [Inspi color](https://www.alanapirrone.com.au/blog/tag/back-to-back+bar+chart)


# ---Comment jai pu avoir la list des data pacbio nanopore sur ENA. JUST TAPER FUSARIUM OXYSPPORUM PACBIO PUIS TELECHARGER LE FICHIER XML PUIS CONVERTIR CE FICHIER SUR CE [SITE](https://conversiontools.io/convert/xml-to-excel)



##### Translate english file into french [here](https://www.onlinedoctranslator.com/app/translationprocess)


##### How I solved this error message when installing Hifiasm `make: g++: Command not found`  I found the solution [here](https://gahee0416.tistory.com/23) by doing `sudo yum install gcc-c++` since I am using Centos OS 7 


###### Phylogenetic tree visualization 


- #### [nice tuto](http://evomics.org/wp-content/uploads/2016/06/TreeEditingVisualization_WoPhylogenomics_CK2017.pdf)



##### A work for Yolande

```


# Libraries
library(ggplot2)


#theme_set(theme_minimal())

#--Data importation
data_humidity = read.csv("data_humidity.csv", sep = ";", h=T , dec = ",")

data_new <- data_humidity                               # Replicate data
data_new$Profondeur <- factor(data_new$Profondeur,      # Reordering group factor levels
                         levels = c("10cm", "20cm", 
                                    "30cm", "40cm", 
                                    "50cm", "60cm",
                                    "70cm", "80cm", 
                                    "90cm", "100cm", 
                                    "110cm", "120cm",
                                    "130cm", "140cm",
                                    "150cm", "160cm"))

#--Plot

p <- ggplot(data_new, aes(x=as.Date(Date), y=Humidite)) +
  geom_line(color="steelblue") + 
  geom_point(color="steelblue", alpha = 1/10) +
  xlab("") +
  theme_bw()+
  #theme_minimal() +
  theme(axis.text.x=element_text(angle=60, hjust=1)) +
  scale_x_date(limit=c(as.Date("2018-07-31"),as.Date("2019-11-07"))) +
  ylim(0,30)+
  facet_wrap(~Profondeur)+
  labs(y = "Soil moisture (mm)", x = "Date")

p






```

[output1](https://github.com/Yedomon/Bric_a_Brac/blob/master/Plot1_6.91_6.91.pdf)

[output2](https://github.com/Yedomon/Bric_a_Brac/blob/master/Plot2_6.91_6.91.pdf)

[dataset](https://github.com/Yedomon/Bric_a_Brac/blob/master/data_humidity.csv)



##### A serious issue today. Just want to get cds translated protein fron annonated genbank file but I struggle alot


Here is the solution.

I gound it [here](https://pypi.org/project/gbseqextractor/).

`gbseqextractor` can do many things...


So I install the tool by doing 


`
pip install gbseqextractor

`


Then I run

```

 gbseqextractor -f kc.gb -prefix china_cds -seqPrefix yuzhi -types CDS -cds_translation


```

I got the cds fatsa nucleotide as well as protein file. Awesome.



##### Calculate Pi for my chloroplast datasets.

I have five assemblies.

I used MAFFT to aligne nucleotide assembly files

then import into DNAsp v6


then GO TO ANALYSIS > DNA POLYMORPHISM

SELECT Pi and click on compute button in order to change The step size  to 50 base pairs, and window length  to 800 base pairs.


The default one give a very narrow bin


After getting the result use ggplot2 to draw the graph of pi following the sliding window following this [tutorial](https://www.r-graph-gallery.com/line_chart_annotation.html)



I found this basic plot [also](https://www.r-graph-gallery.com/200-change-color-in-lineplot-following-y-value.html) and ggplot2 based [plot](https://stackoverflow.com/questions/35039846/change-line-color-depending-on-y-value-with-ggplot2?lq=1)


for annotation as well as flche et autre I think [BBC style](https://bbc.github.io/rcookbook/) will be required. 


[geom_area](https://www.r-bloggers.com/2017/09/how-to-make-a-line-chart-with-ggplot2/) to be fancy..but geom area coloring follwing a y axis



finally selest this [one](https://support.sisense.com/hc/en-us/community/posts/360038200234-Plotting-a-Gradient-Line-in-R)

[theme modification ggplot2](https://ggplot2.tidyverse.org/reference/theme.html)



I foun a tuto [here](https://msu.edu/course/zol/855/f09/workshop_111109.html) and the authors tuto [here](https://www.researchgate.net/publication/24309060_DNA_sequence_polymorphism_analysis_using_DnaSP/link/0912f50a8c3524b3c7000000/download) AND [HERE](http://www.ub.edu/dnasp/DnaSP6_Documentation_6.12.pdf)

i JUST SEE THAT IT IS POSSIBLE TO ASSIGN CODING REGIONS DEFIN THE TYPE OF DATA DNA/RNA..CHLOROPLAST OT MITO ...


This guy did a mistake [here](https://www.biostars.org/p/457878/)






convert chloae annotation gff to genbank

response [here](https://www.biostars.org/p/2492/)


how I ran fastp


INSTALLATION


```

# create env and install tools
$ conda create --yes -n qc fastp fastqc multiqc

# activate env
$ conda activate qc

```

RUN

```bash

#!/bin/bash

set -e

#---Handles permissions of files for all users (a), take away (-) the permission to write (w)

chmod a-w *.gz

#---Create link for the raw data

cd ~/data_analysis/01.Reads_quality_control 

ln -fs ~/datafiles/fusarium_oxysporum_human_nrrl47514_mrl8996/illumina_raw_data/* .

#---Let's activate the qc conda environment

source activate reads_qc_env

#---Let's run fastqc on the raw data

fastqc *.gz

#---Let's run fastp

fastp --detect_adapter_for_pe \
       --overrepresentation_analysis \
       --correction --cut_right --thread 2 \
       --html ../02.Trimming/FoHuman.fastp.html --json ../02.Trimming/FoHuman.fastp.json \
       -i SRR9694936_1.fastq.gz -I SRR9694936_2.fastq.gz \
       -o ../02.Trimming/FoHuman_R1.fastq.gz -O ../02.Trimming/FoHuman_R2.fastq.gz 

#---Let's run fastqc again on the trimmed data

fastqc *

#--Let's run multiQC on both untrimmed and trimmed files

cd ../

multiqc 01.Reads_quality_control 02.Trimming 

mv multiqc_* 03.Post_trimming_quality_control

#---Desactivate the reads QC conda environment

source deactivate reads_qc_env

#---END


```


Ideas


[Genome-wide identification and analysis of cystatin family genes in Sorghum (Sorghum bicolor (L.) Moench)](https://peerj.com/articles/10617/)


[SSR SESAME](Morphological and genetic diversity assessment of sesame (Sesamum indicum L.) accessions differing in origin)




[How to concatenate multiple sequence alignment](https://www.biostars.org/p/332853/)
