---
title: "Lync Server 2013: Detección automática de movilidad con implementaciones híbridas"
TOCTitle: Configurar la detección automática para movilidad con implementaciones híbridas
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48277214
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la detección automática para movilidad con implementaciones híbridas en Lync Server 2013

 

_**Última modificación del tema:** 2014-06-18_

Las implementaciones híbridas son configuraciones que utilizan tanto el servicio de nube de Microsoft Lync Online, como la implementación local. En este tipo de configuración, el servicio de detección automática puede determinar dónde está ubicado realmente el usuario. Es decir, la detección automática ayuda a encontrar la cuenta de usuario y el lugar en el que el servidor hospeda la cuenta del usuario, independientemente de si es en una implementación local o en la implementación de Skype Empresarial Online.

Por ejemplo, si una cuenta de usuario se hospeda en un servidor en Skype Empresarial Online, el intento de localizar al usuario se realizará como a continuación, en un proceso conocido como *detectabilidad*:

  - El usuario inicia un intento de conexión en la implementación local, **contoso.com**.

  - Se envía el intento a lyncdiscover.contoso.com, el nombre de DNS asociado al servicio de detección automática.

  - La detección automática remite al supuesto grupo de servidores de registro en la implementación local de contoso.com y recibe información sobre el servidor principal real del usuario hospedado en Skype Empresarial Online. La detección automática envía al usuario una derivación al servicio de detección automática en línea de **lync.com**.

  - El usuario inicia un intento de conexión al servicio de detección automática en línea de lync.com y puede localizar la cuenta de usuario y el servidor principal del usuario.

Para que clientes móviles puedan descubrir la implementación en la que se encuentra el servidor principal del usuario, debe configurar el servicio de detección automática con un localizador de recursos uniforme (URL) nuevo. Para configurar el servicio de detección automática, haga lo siguiente:

## Configurar la detección automática para implementaciones híbridas

1.  Se usa Get-CsHostingProvider para recuperar el valor del atributo ProxyFQDN.

2.  Desde el Shell de administración de Lync Server, escriba
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Donde \[identity\] se sustituye por el nombre de dominio del espacio de direcciones SIP compartido.

## Vea también

#### Otros recursos

[Get-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostingProvider)

