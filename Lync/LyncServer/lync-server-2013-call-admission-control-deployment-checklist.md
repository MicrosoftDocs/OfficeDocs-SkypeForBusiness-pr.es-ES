---
title: Lista comprobación para implement. control admisión de llamadas en Lync Server 2013
TOCTitle: Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48276800
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-22_

Use la lista de comprobación proporcionada a continuación para comprobar si ha completado todas las tareas de configuración necesarias para implementar el control de admisión de llamadas.

  - Si implementa uno o más servidores perimetrales, debe agregar cada dirección IP de interfaz externa a la lista de subredes de los parámetros de configuración de red, con una máscara de bits de 32. También debe asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.
    

    > [!NOTE]
    > Los servidores perimetrales no son necesarios para implementar CAC.



  - Asegúrese de que el servicio de control de admisión de llamadas esté habilitado, ya sea mediante el Panel de control de Lync Server o ejecutando el cmdlet como se indica en [Habilitar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales. Para ello, use el Generador de topologías. Si aparece una advertencia durante la publicación, *no* la ignore.

  - Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red. También es fundamental que cada subred esté asociada con un sitio de red, tal y como se explica en [Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.

