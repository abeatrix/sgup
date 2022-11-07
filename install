#!/usr/bin/env bash

MODE=$1

if [[ -z $(echo $1) ]]; then
    multipass launch --name sg --cpus 8 --mem 16G --disk 50G
    multipass info sg | grep -i ip | cut -d ":" -f 2 | xargs
    multipass exec sg -- bash -c "curl -sfL https://raw.githubusercontent.com/abeatrix/sgup/main/k3s.sh | bash"
    sleep 5
    SGVMIP=$(multipass info sg | grep -i ip | cut -d ":" -f 2 | xargs)
    open http://"$SGVMIP"
else
    echo "$MODE"
fi
