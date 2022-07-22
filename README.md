# vpn-auto-otp

function vpnlab {
echo OTP;read otp_code && sudo -S <<< 'ROOT_PASSWORD' echo && { printf 'VPN_PASSWORD\n'; sleep 1; printf "$otp_code\n"; } | sudo openconnect VPN_IP --servercert pin-sha256:XXXXXXXXXXXXXXXXX --user=VPN_USER --authgroup=VPN_GROUP --passwd-on-stdin
}

function vpnlab2 {
otp_code=$1 && sudo -S <<< 'ROOT_PASSWORD' echo && { printf 'VPN_PASSWORD\n'; sleep 1; printf "$otp_code\n"; } | sudo openconnect VPN_IP --servercert pin-sha256:XXXXXXXXXXXXXXXXX --user=VPN_USER --authgroup=VPN_GROUP --passwd-on-stdin
}
