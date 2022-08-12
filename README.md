# az-cli-aliases

> $ cat ~/.bash_aliases
```
export AZ_SUB="~~~~~~"
export RG="koc-rg"
export ER="ko-er"
export KO_HUB="koc-vhub"
export KO_RT_ID="/subscriptions/${AZ_SUB}/resourceGroups/${RG}/providers/Microsoft.Network/virtualHubs/${HUB_KO}/hubRouteTables/defaultRouteTable"

alias so='source ~/.bash_aliases'

alias az-er-pri-arp='az network express-route list-arp-tables -n ${ER} --path primary --peering-name AzurePrivatePeering -g ${RG}'
alias az-er-pri-route='az network express-route list-route-tables -n ${ER} --path primary --peering-name AzurePrivatePeering -g ${RG}'
alias az-er-pri-route-sum='az network express-route list-route-tables-summary -n ${ER} --path primary --peering-name AzurePrivatePeering -g ${RG}'

alias az-er-sec-arp='az network express-route list-arp-tables -n ${ER} --path secondary --peering-name AzurePrivatePeering -g ${RG}'
alias az-er-sec-route='az network express-route list-route-tables -n ${ER} --path secondary --peering-name AzurePrivatePeering -g ${RG}'
alias az-er-sec-route-sum='az network express-route list-route-tables-summary -n ${ER} --path secondary --peering-name AzurePrivatePeering -g ${RG}'

alias az-hub-ko-route='az network vhub get-effective-routes --resource-type VpnConnection --resource-id ${KO_RT_ID} -n ${KO_HUB} -g ${RG} -o table | tail -n+3 | awk -F"/s" "{print \$1} END{print \"Total Routes:\",NR}"'
```

