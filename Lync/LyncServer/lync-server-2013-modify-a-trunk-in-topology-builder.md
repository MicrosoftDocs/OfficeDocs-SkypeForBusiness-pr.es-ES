---
title: "Mod. d’une jonction dans le générateur de topologie dans Lync Server 2013"
TOCTitle: "Mod. d’une jonction dans le générateur de topologie dans Lync Server 2013"
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49889350
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificación de un tronco en el Generador de topologías en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Siga estos pasos para modificar la dirección IP de medios alternativa y el identificador alternativo por omisión de tronco.

## Para modificar la dirección IP de medios alternativa de un tronco

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute le cmdlet Set-CsPstnGateway y modifique el campo AlternateBypassId en el Shell de administración de Lync Server.
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

## Para modificar el BypassID alternativo de un tronco

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsPstnGateway y modifique el campo AlternateBypassId en el Shell de administración de Lync Server.
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

