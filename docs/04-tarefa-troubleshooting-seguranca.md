# Etapa 4: Troubleshooting e Redes no VirtualBox

## 🎯 Objetivo
Solucionar travamentos comuns do VirtualBox ao lidar com sistemas legados e mitigar riscos de segurança através do isolamento de placas de rede virtuais.

---

## 📑 Roteiro de Execução

1.  **Troubleshooting de Integração (Se necessário):**
    *   Se o mouse travar ou sumir após a instalação, vá nas configurações da VM no VirtualBox, aba **Sistema** -> **Dispositivo de Apontamento** e mude de `Multi-touch Tablet` para `Mouse PS/2`.
2.  **Configuração de Rede Segura (Isolamento de Vulnerabilidades):**
    *   O Windows XP é vulnerável a ataques modernos de rede distribuída (como o exploit *EternalBlue* / *WannaCry*).
    *   Abra as configurações da VM no VirtualBox com ela desligada. Vá na aba **Rede**.
    *   No campo **Conectado a:** altere a opção padrão `NAT` para **Não Conectado** ou **Rede Interna (Internal Network)**.
    *   Isso garante que o sistema compartilhe arquivos com outras VMs do laboratório (se necessário), mas fique totalmente blindado e invisível contra varreduras e ataques vindos da Internet real.

---

## 📝 Entregáveis desta Etapa

### 📸 [EVIDÊNCIA]
<img width="807" height="599" alt="image" src="https://github.com/user-attachments/assets/893310de-7c97-48a0-8fba-ae187b55bb34" />


### ❓ [QUESTÃO 4]
Se mantivéssemos o adaptador de rede da máquina virtual do Windows XP configurado no modo "Placa em modo Bridge (Bridged Adapter)" conectada à rede Wi-Fi/cabeada pública da instituição, quais seriam as consequências imediatas em termos de segurança cibernética para o laboratório e para a VM?

**Sua Resposta:**
> Configurar o Windows XP em modo Bridge em uma rede pública elimina a blindagem da máquina virtual, dando a ela um IP próprio e tornando-a visível para todos. Devido a falhas críticas sem correção desde 2014, a VM pode ser invadida e infectada por vírus de forma automatizada em poucos minutos. O maior perigo é que, uma vez dominada, ela serve de ponte para hackers atacarem os computadores modernos do laboratório por dentro da rede. Isso gerará alertas de segurança e fará a TI bloquear a internet do laboratório inteiro. Por isso, deve-se usar apenas os modos NAT ou Rede Interna.

---
### 🏁 FIM DA ATIVIDADE
Com todas as seções preenchidas e imagens anexadas à pasta `/assets` do seu repositório local, execute os comandos do Git para registrar e subir sua atividade:

```bash
git add .
git commit -m "feat: conclusao do laboratorio de instalacao do winxp no virtualbox"
git push origin main
