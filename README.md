# My-final-Project-for-CNE-350  

  
### A function that lets the user pick an interface to use with Pi-hole

#!/bin/bash  
chooseInterface() {

    local interfacesList
    local interfaceCount

    interfaceCount=$(printf "%s\n" "${availableInterfaces}" | wc -l)

    if [[ "${interfaceCount}" -eq 1 ]]; then
       
        PIHOLE_INTERFACE="${availableInterfaces}"
    
    else
        
        status="ON"

        for interface in ${availableInterfaces}; do
            
            interfacesList="${interfacesList}${interface} available ${status} "
           
            status="OFF"
        done
        
    printf "  %b Using interface: %s\\n" "${INFO}" "${PIHOLE_INTERFACE}"
}
