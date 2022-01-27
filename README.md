# Hello this is my attempt to generate real seeming bacterial tRNAs

I pulled down tons of Enterobacterales genomes using the ncbi_dataset tool, and then ran tRNAscan-SE on all of them. I kept the sequences and am trying to generate realistic Arg tRNAs.
I chose Arg because in my exploration of the data because
1. They had the most normal distribution of quality scores
2. They were very abundant (>1000) non-unique (>100) unique
3. There are several Modomics Arg tRNAs that seem different yet similar enough
4. I just like Arg :)

---

1/16/2022
My LSTM model can generate tRNAs that fool BLAST and tRNAscan-SE, but the issue is that I don't know if they 
are fooling these programs, or they have simply remembered their inputs and re-created them. I would like 
to write a script that performs EMBOSS's NEEDLE alignment (global alignement) to check if the generated tRNA 
100% matches one of the inputs. If that is the case, I have currently no idea what to do :P


1/23/2022
They are somewhat generating new sequences. I implemented a distance measure, and I believe the differences
I am seeing are due to the "temperature" setting I have, rather than the model actually understanding that
it needs to generate new tRNAs. Either way, if the sequence differs too too much from the training data
it is generally noted as a pseudogene by tRNAscan-SE, or has wonky secondary structure.


That being said I think I would like to truly randomize the input seed as such. Currently the seed is a window
or 'R' characters FRAG_SIZE-1 long. I think it would be better to have something like this:<br>
    ['R', 'R', 'R', 'char', 'char', 'char', 'char', 'char', 'char', 'R', 'R', 'R']<br>
This example is a window that is 12 characters long. These characters can be the remaining english alphabet
that isn't ['R', 'P', 'A', 'G', 'T', 'C']
    
