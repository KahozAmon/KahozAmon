MODELO OSI
import streamlit as st

# Dados das camadas
osi_layers = [
    {"name": "Física", "desc": "Transmissão dos bits pelo meio físico.", "examples": "Wi-Fi, Ethernet, Bluetooth"},
    {"name": "Enlace", "desc": "Entrega confiável entre dispositivos locais.", "examples": "Switches, MAC, Wi-Fi (802.11)"},
    {"name": "Rede", "desc": "Endereçamento lógico e roteamento.", "examples": "IPv4, IPv6, Roteadores"},
    {"name": "Transporte", "desc": "Entrega fim a fim, confiável ou não.", "examples": "TCP, UDP"},
    {"name": "Sessão", "desc": "Gerencia sessões de comunicação.", "examples": "NetBIOS, RPC"},
    {"name": "Apresentação", "desc": "Formatação, compressão e criptografia.", "examples": "TLS/SSL, JPEG, ASCII"},
    {"name": "Aplicação", "desc": "Interface com o usuário.", "examples": "HTTP, FTP, DNS, SMTP"}
]

tcpip_layers = [
    {"name": "Acesso à Rede", "desc": "Equivale a Física + Enlace do OSI.", "examples": "Ethernet, Wi-Fi, ARP"},
    {"name": "Internet", "desc": "Equivale à Rede do OSI.", "examples": "IP, ICMP"},
    {"name": "Transporte", "desc": "Equivale à Transporte do OSI.", "examples": "TCP, UDP"},
    {"name": "Aplicação", "desc": "Equivale a Sessão + Apresentação + Aplicação do OSI.", "examples": "HTTP, DNS, FTP"}
]

# Layout
st.title("🌐 Modelos de Redes: OSI vs TCP/IP")

col1, col2 = st.columns(2)

with col1:
    st.header("Modelo OSI (7 camadas)")
    for layer in osi_layers:
        if st.button(layer["name"], key=layer["name"]):
            st.info(f"**Descrição:** {layer['desc']}\n\n**Exemplos:** {layer['examples']}")

with col2:
    st.header("Modelo TCP/IP (4 camadas)")
    for layer in tcpip_layers:
        if st.button(layer["name"], key=layer["name"]):
            st.success(f"**Descrição:** {layer['desc']}\n\n**Exemplos:** {layer['examples']}")