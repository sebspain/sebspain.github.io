---
layout: page
title: Code Tests
---

A series of tests of code/syntax highlighting

###Shell Script###

```{sh}
#!/bin/bash
dir=/srv/http/$1
type=$2

if  [[ "$type" == "daily" ]];
then
suffix=$(date +%A)
elif [[ "$type" == "weekly" ]];
then
suffix=week_$(($(date +%V) % 4 + 1)) #get modulus of week number so that only 4 kept, 1 is added to number them 1-4
else
suffix=$(date +%B)
fi

if [[ "$1" == "cloud" ]];
then
tar_options="--exclude="$dir/data" --exclude="$dir/data/*" "
elif [[ "$1" == "piwik" ]];
then
tar_options="--exclude="$dir/tmp" --exclude="$dir/tmp/*" "
else
tar_options=""
fi

#echo $tar_options
tar -cp ${tar_options} $dir | gpg --encrypt -a -r "Seb Spain" -o /tmp/http_${1}_${suffix}.tar.gz.gpg

if [[ "$type" != "" ]];
then
ncftpput -f ~/.ftp_cred /$type  /tmp/http_${1}_${suffix}.tar.gz.gpg
else
ncftpput -f ~/.ftp_cred /monthly  /tmp/http_${db_name}_${suffix}.tar.gz.gpg
fi

```

###R script###

```{r}
args<-commandArgs(TRUE);

data<-read.table(args[1], header=T)
data$x<-data$conv/100
data$ln<-log(1/(1-data$x))

pdf("output.pdf")
plot(data$t, data$conv, xlab="Time / min.", ylab="Monomer Conversion / %", pch=16, ylim=c(0,100), xlim=c(0,1440))
plot(data$t, data$ln, xlab="Time / min.", ylab="ln(1/1-x)", pch=16, xlim=c(0,1440), ylim=c(0,4))
dev.off()

```


###$$\LaTeX$$###

```{tex}
\frac{x}{y}

```

$
\frac{x}{y}
$ 
