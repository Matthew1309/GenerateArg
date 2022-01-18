# Hello this is my attempt to generate real seeming bacterial tRNAs

I pulled down tons of Enterobacterales genomes using the ncbi_dataset tool, and then ran tRNAscan-SE on all of them. I kept the sequences and am trying to generate realistic Arg tRNAs.
I chose Arg because in my exploration of the data because
1. They had the most normal distribution of quality scores
2. They were very abundant (>1000) non-unique (>100) unique
3. There are several Modomics Arg tRNAs that seem different yet similar enough
4. I just like Arg :)

---

My LSTM model can generate tRNAs that fool BLAST and tRNAscan-SE, but the issue is that I don't know if they 
are fooling these programs, or they have simply remembered their inputs and re-created them. I would like 
to write a script that performs EMBOSS's NEEDLE alignment (global alignement) to check if the generated tRNA 
100% matches one of the inputs. If that is the case, I have currently no idea what to do :P
