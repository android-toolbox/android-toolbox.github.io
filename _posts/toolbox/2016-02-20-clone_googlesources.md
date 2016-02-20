---
title:      Clone Google Sources
category:	blog
tags:		sources
layout:     post
featured:   /assets/images/box.png
---
    #!/bin/bash
    
    wget -q https://android.googlesource.com/?format=TEXT -O - | while read SAMPLE
    do
    	REPOSITORY=$(echo $SAMPLE | sed '1,$s#/#_#g')
    
    	echo echo $SAMPLE to $REPOSITORY
    
    	git clone -q https://android.googlesource.com/$SAMPLE $REPOSITORY
    done
    
{% gist ecee7a2c85b8ae112989 %}
