# practica_1_linux
#!/bin/bash

opcion='x'
codi_p='xx'
codi_e='xxx'

echo "Introduce una opción:"
while [ "$opcion" != 'q' ]; do
    read opcion
    case $opcion in
        q)
            echo "Saliendo de la aplicación"
            exit
            ;;
        lp)
            cut -d',' -f7,8 cities.csv | column -s',' -t | uniq | head -n 3
            ;;
        sc)
            echo "Introduce el nombre de un país:"
            read pais
            if grep -q "$pais" cities.csv; then
                cut -d',' -f7,8 cities.csv > pais.csv
                codi_p="$(grep "$pais" pais.csv | cut -d',' -f1 | uniq)"
                echo "$codi_p"
            elif [ -z "$pais" ]; then
                echo "Opción no válida"
            else
                codi_p='XX'
                echo "$codi_p"
            fi
            ;;
        se)
            echo "Introduce el nombre de un estado:"
            read estado
            if grep -q "$estado" cities.csv; then
                cut -d',' -f4,5 cities.csv > estados.csv
                codi_e="$(grep "$estado" estados.csv | cut -d',' -f1 | uniq)"
                echo "$codi_e"
            elif [ -z "$estado" ]; then
                echo "$codi_e"
            else
                codi_e='XX'
                echo "$codi_e"
            fi
            ;;
        le)
            cut -d',' -f4,5,8 cities.csv > paises.csv
            grep "$pais" paises.csv | cut -d',' -f1,2 | uniq
            ;;
        lcp)  
            grep -q "$pais" cities.csv && cut -d',' -f8 cities.csv | grep "$pais" | cu$
            ;;
        ecp)
            cut -d',' -f7,8 cities.csv > pais.csv
            codi_p="$(grep "$pais" pais.csv | cut -d',' -f1 | uniq)"
            cut -d',' -f4,5,8 cities.csv > "${codi_p}.csv"
        lce)
            cut -d',' -f2,4,11 cities.csv > lce.csv
            grep "$estado" lce.csv | cut -d',' -f1,3 | column -s',' -t | uniq > "${cod$
            ;;
        gwd)
            echo "Introduce el nombre de una población:"
            read poblacio
            if grep -q "$poblacio" lce.csv; then
                informacio_wikidata_Del_URL > "$(grep "$poblacio" lce.csv | cut -d',' $
            ;;
        est)
            nord=$(auk'$9 > 0 {count++} END {print count}' cities.csv)
            sud=$(auk'$9 < 0 {count++} END {print count}' cities.csv)
            est=$(auk'$10 > 0 {count++} END {print count}' cities.csv)
            oest=$(auk'$10 < 0 {count++} END {print count}' cities.csv)
            no_ubic=$(auk'$9 == 0 && $10 == 0 {count++} END {print count}' cities.csv)
            echo "Nord $nord Sud $sud Est $est Oest $oest No ubic $no_ubic"
            ;;
        *)  
            echo "Opción no reconocida"
            ;;
    esac
    echo "Introduce una opción:"
done
        
echo "Saliendo de la aplicación"
