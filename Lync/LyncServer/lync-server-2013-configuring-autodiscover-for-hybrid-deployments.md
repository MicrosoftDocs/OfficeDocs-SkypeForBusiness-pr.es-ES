---
title: Configurar la detección automática para implementaciones híbridas
TOCTitle: Configurar la detección automática para implementaciones híbridas
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945653(v=OCS.15)
ms:contentKeyID: 52061761
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la detección automática para implementaciones híbridas

 

_**Última modificación del tema:** 2012-12-12_

Las implementaciones híbridas son configuraciones que utilizan tanto el servicio de nube de Microsoft Lync Online como la implementación local. En este tipo de configuración, el servicio Detección automática puede determinar dónde está ubicado realmente el usuario. Es decir, Detección automática ayuda a encontrar la cuenta de usuario y el lugar en el que el servidor hospeda la cuenta del usuario, independientemente de si es en una implementación local o en la implementación de Skype Empresarial Online.

Por ejemplo, si una cuenta de usuario se hospeda en un servidor en Skype Empresarial Online, el intento de localizar al usuario se realizará según se indica a continuación, en un proceso conocido como *detectabilidad*:

  - El usuario inicia un intento de conexión en la implementación local, **contoso.com**.

  - Se envía el intento a lyncdiscover.contoso.com, el nombre de DNS asociado al servicio de detección automática.

  - Detección automática remite al supuesto grupo de servidores de registro en la implementación local de contoso.com y recibe información sobre el servidor principal real del usuario hospedado en Skype Empresarial Online. Tras ello, Detección automática envía al usuario una derivación al servicio Detección automática en línea de **lync.com**.

  - El usuario inicia un intento de conexión al servicio Detección automática en línea de lync.com y puede localizar la cuenta de usuario y el servidor principal del usuario.

Para que los clientes puedan detectar la implementación en la que se encuentra el servidor principal del usuario, debe configurar el servicio Detección automática con un localizador de recursos uniforme (URL) nuevo. Para ello, haga lo siguiente:

## Configuración de Detección automática para implementaciones híbridas

1.  En el tema [Requisitos del servicio Detección automática para Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), se utiliza Get-CsHostingProvider para recuperar el valor del atributo ProxyFQDN.

2.  En el Shell de administración de Lync Server, escriba:
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Donde \[identity\] se sustituye por el nombre de dominio del espacio de direcciones SIP compartido.

## Vea también

#### Otros recursos

[Get-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostingProvider)

