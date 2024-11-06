library(Cairo)
setwd("/molbio/projects/liposits/MA-speciments_GnRH-cell-heterogenity/")
my.ma <- read.table("ma.orig.txt",row.names = 1)

# find first bifurcation point in MA group to find most likely subgroups 
my.dist.ma <- dist(my.ma)
clust.ma <- hclust(my.dist.ma)
Cairo( width = 2560, height = 1820, file = "euclidian.dist.MA.jpg", type = "jpeg", dpi = 300)
plot(clust.ma, ann =F)
dev.off()

# compare subgroups to check if the two are significantly different
my.ma.clust1.id <- c("MA_01" , "MA_03" , "MA_04" , "MA_05" , "MA_12" , "MA_13" , "MA_14" , "MA_15" , "MA_17" , "MA_21" , "MA_22" , "MA_23" , "MA_24" , "MA_26" , "MA_27" , "MA_33" , "MA_34" , "MA_35" , "MA_44")
my.ma.clust2.id <- c("MA_02" , "MA_07" , "MA_08" , "MA_11" , "MA_18" , "MA_28" , "MA_31" , "MA_32" , "MA_37" , "MA_38" , "MA_41" , "MA_47" , "MA_48")
my.ma.clust1 <- my.ma [rownames(my.ma) %in% my.ma.clust1.id,]
my.ma.clust2 <- my.ma [rownames(my.ma) %in% my.ma.clust2.id,]
wilcox.test(my.ma.clust1, my.ma.clust2,paired = F)
# 2.36e-06


# compare both to Young group 
my.young <- read.table("young.orig.txt", row.names = 1)

wilcox.test(my.clust1, my.young$V2, paired = F)
#0.4282
wilcox.test(my.clust2, my.young$V2, paired = F)
# 3.173e-07
