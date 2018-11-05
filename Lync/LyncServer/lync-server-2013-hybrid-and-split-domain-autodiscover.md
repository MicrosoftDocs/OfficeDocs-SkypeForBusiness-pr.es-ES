---
title: 'Implementación híbrida y dominio dividido: detección automática'
TOCTitle: 'Implementación híbrida y dominio dividido: detección automática'
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945652(v=OCS.15)
ms:contentKeyID: 52061748
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación híbrida y dominio dividido: detección automática

 

_**Última modificación del tema:** 2013-02-14_

Un espacio de direcciones SIP compartido, también conocido como una implementación de *dominio dividido* o una implementación *híbrida*, es una configuración en la que los usuarios se implementan en toda una implementación local y en un entorno en línea. El resultado deseado es que un usuario inicie sesión en la implementación y se le redirija a la ubicación de su servidor principal, independientemente de dónde se encuentre su servidor principal (in situ o en línea). Para lograrlo, la función Detección automática de Lync Server 2013 se utiliza para redirigir al usuario en línea hacia la topología en línea. Esto puede realizarse configurando el localizador uniforme de recursos (URL) de Detección automática mediante el Shell de administración de Lync Server y los cmdlets **Get-CsHostingProvider** y **Set-CsHostingProvider**.

## Movilidad para la implementación de dominio dividido

Deberá recopilar y registrar los siguientes atributos implementados:

  - En el Shell de administración de Lync Server, escriba:
    
        Get-CsHostingProvider

  - En los resultados, busque el proveedor en línea que tenga el atributo **ProxyFQDN**. Por ejemplo, sipfed.online.lync.com

  - Registre el valor del ProxyFQDN.

  - Habilite la federación en el Panel de control de Lync Server local, permitiendo la federación con el proveedor en línea.

  - Habilite la federación para el proveedor en línea. Todos los usuarios en línea están habilitados de manera predeterminada para la federación de dominios y pueden comunicarse con todos los dominios.

  - Si desea definir dominios restringidos y permitidos, determine de manera explícita los dominios que permitirá y los que restringirá.

  - Para la federación en línea, debe planificar registros host (A o AAAA, si utiliza IPv6) de DNS, certificados y excepciones de firewall. Asimismo, debe configurar las directivas de federación. Para obtener información detallada, consulte [Planeación de federación de Lync Server y Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

