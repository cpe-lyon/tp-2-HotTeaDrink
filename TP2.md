**Variable d’environnement**

1. Bash trouve les commandes dans le dossier /usr/bin
1. Il s’agit de la variable home.
1. LANG : The current locales langage

PWD : Path to current dirrectory

OLDPWD : Path to old dirrectory

SHELL : The Path of the current user’s shell, such as bash or zsh

1. ![](Aspose.Words.6777e07f-0ecc-4468-83bb-af567e752148.001.png)

\4. ![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.001.png)

\5. La commande Bash spécifie juste le shell à utiliser. Ici un shell bash. Cette variable locale n’existe plus car celle-ci a été initialisé dans un autre shell bash.

\6. La variable MY\_VAR exite toujours en variable d’environnement. Car celle-ci a été initialisé dans un autre shell bash  (le shell ubuntu par default est bash). N’étant pas une variable locale, elle n’est pas limitée à être utilisé dans son shell d’initialisation.

\7. ![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.002.png)

\8. ![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.003.png)

![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.004.png)

\9. Donner une valeur vide initialise la variable, elle peut donc être utilisé là ou si l’on utilise unset sur une varible son contenu va la supprimer.

\10. ![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.005.png)

Programmation Bash

![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.006.png)

Exercice 2

![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.007.png)

Exercice 3

![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.008.png)

Exercice 4

![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.009.png)

Exercice 5

![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.010.png)

Exercice 6

![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.011.png)

Exercice 7

\1.

![](Aspose.Words.6fecc595-10fd-4f51-a17c-1e07d0ed48b4.012.png)

\2.

```BASH
for i in "${array[@]}"; do
    #Remove padding zeroes, if any
    i=$(( $i ))
    # If element of arr is not in seen, add it as a key to seen
    if [ -z "${seen[i]}" ]; then
        seen[i]=1
    else
        echo "Merci de ne pas mettre de doublons"
        exit 
    fi
done

# Bubble sort 
for ((i = 0; i<5; i++))
do

    for((j = 0; j<5-i-1; j++))
    do
    
        if [ ${array[j]} -gt ${array[$((j+1))]} ]
        then
            # swap
            temp=${array[j]} 
            array[$j]=${array[$((j+1))]}  
            array[$((j+1))]=$temp
        fi
    done
done

echo "Voici le tableau:"
echo ${array[*]}

min=${array[0]}
max=${array[-1]}

sum=0
for i in "${array[@]}"; do
 sum=$(("$sum"+"$i"))
done
moyenne=$(($sum/${#array[@]}))

echo "Max:$max, Min:$min, Moyenne:$moyenne"
```
