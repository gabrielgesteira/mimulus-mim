## Escola Superior de Agricultura “Luiz de Queiroz” 
### Programa de Pós graduação em Genética e Melhoramento de Plantas
### Disciplina: Biometria de Marcadores Genéticos

**Alunos:**
- Emanoel Martins
- Gabriel Gesteira
- Jackeline Borba
- Pedro Barbosa

## Mapeamento de QTLs - _Mimulus spp._
### Mapeamento por Intervalo Múltiplo - _Multiple Interval Mapping_ (MIM)

Nesta seção apresentamos os detalhes e os resultados obtidos no mapeamento de QTLs em _Mimulus spp._ utilizando o método MIM (_Multiple Interval Mapping_). Esta atividade foi proposta pelo Prof. Augusto Garcia na disciplina "Biometria de Marcadores Genéticos", do Programa de Pós-Graduação em Genética e Melhoramento de Plantas da ESALQ/USP.

Conforme mencionado, o objetivo deste trabalho foi realizar o mapeamento de QTLs em _Mimulus spp._, com base em dados genotípicos presentes em um [**mapa genético elaborado anteriormente**](https://gabrielgesteira.github.io/Mapa-Mimulus/) utilizando o pacote _Onemap_. Para o mapeamento de QTLs foram utilizados dados genotípicos obtidos de 418 marcadores moleculares e dados fenotípicos coletados em campo para o caráter 'número de pólens não-viáveis'. Desta vez, o método empregado foi o mapeamento por intervalo múltiplo (_Multiple Interval Mapping_ - MIM). Também realizamos o mapeamento por intervalo composto (_Composite Interval Mapping_ - CIM) com o objetivo de comparar os resultados obtidos por ambos os métodos. Todas as análises foram realizadas com o auxílio do pacote estatístico R/qtl.

[**Clique aqui**](https://gabrielgesteira.github.io/mimulus-mim/mimulus-mim.html) para visualizar o script utilizado e os resultados obtidos com as análises.

## Vídeo: passo-a-passo

Disponibilizamos um vídeo no YouTube onde detalhamos por etapas os procedimentos realizados para o mapeamento dos QTLs pelo método MIM. Para visualizar o vídeo, [**clique aqui**]().

Também realizamos um trabalho semelhante, com os mesmos dados, visando mapear QTLs e comparar os resultados obtidos entre os métodos _Interval Mapping_ (IM) e _Composite Interval Mapping_ (CIM). O script elaborado para realizar as análises, bem como os resultados e um vídeo explicativo sobre o assunto podem ser acessados [**clicando aqui**](https://gabrielgesteira.github.io/mimulus-qtl/). 

## Material and Methods

### Linkage map

The linkage map was previously constructed from a F2 mapping population obtained from an interspecific cross between the _Mimulus guttatus_ and _M. nasulus_, with 287 genotyped individuals, using 418 markers. The package utilized to obtain the linkage groups and order the markers within each group was _OneMap_ v.2.0 (version under development), and the _MapChart_ 2.3 was used to produce the chart of genetic linkage map.

### QTL Analysis

This linkage map was then utilized to QTL mapping using the R/qtl package (Broman _et al._, 2003). Three methods of QTL mapping were performed and compared against each other, showing its differences and advantages. The methods were the following: Interval Mapping (IM), Composite Interval Mapping (CIM), and Multiple Interval Mapping (MIM). The trait chosen as phenotypic data was non-viable pollen (nv).
In the IM method a genome scan is carried out in every cM of the genome utilizing the information of the markers to calculate the genotype probability of pseudo markers between any pair of flanking markers, using, in this case, Haley-Knott regression (HK). The CIM method is similar, but now an interval test is realized together with regression analysis for each interval within the window size of 10 cM. All the significant markers outside of this interval of study were used as cofactors in the statistical model, thus reducing the effect of linked QTLs. The number of markers to be used as cofactors was chosen based on _stepwiseqtl()_ function, which indicated the number of significative markers for the trait. The method applied was also HK. 
Last, we performed the MIM mapping. In this method multiple intervals and multiple QTL are analyzed simultaneously by including the significant QTLs as cofactors in the model. This method allows test for epistasis effects, besides the additive and dominance effects also obtained by the two other methods. To fit the best model and then discover the number of QTLs to be used in the model it was applied the _scantwo()_ and _stepwiseqtl()_ functions. The threshold to determine significance in all the three cases was defined upon 1000 permutations and α = 0.05. For this particular trait, no epistasis effect were indicated. As results, it was concluded that in the first two methods only one QTL was appointed, but in the last one, evidences were found for three QTLs and no interaction.

The code for MIM QTL mapping and the final map with the QTLs located in their respective positions can be viewed by [**clicking here**](https://gabrielgesteira.github.io/mimulus-mim/mimulus-mim.html).