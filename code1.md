# code-BNP-PARIPAS
#### importaion des differentes tables par lot
apprent=read.csv("train.csv",header = T, sep=",",dec=".")
test=read.csv("test.csv",header = T, sep=",",dec=".")
table(base$target)
table(is.na(base$target)) # pas de données manquantes dans la variable cible de la bse d'appentissage
library("FactoMineR", lib.loc="C:/Program Files/R/R-3.2.0/library")
library("missMDA", lib.loc="C:/Program Files/R/R-3.2.0/library")
library("rattle", lib.loc="C:/Program Files/R/R-3.2.0/library")

memory.limit(size=8000)

reg=lm(target~.,data=base)

type=c()
for (i in 3:133) type[i]=is.double(base[,i])
qua=which(type==0)

acp=PCA(apprent, scale.unit = TRUE, ncp = 5, ind.sup = NULL, 
    quanti.sup = NULL, quali.sup = qua, row.w = NULL, 
    col.w = NULL, graph = TRUE, axes = c(1,2))
memory.limit()
