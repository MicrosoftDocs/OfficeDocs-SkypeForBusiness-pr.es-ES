---
title: "Lync Server 2013 : Conf. requise pour l’infrastructure Active Directory"
TOCTitle: Requisitos de infraestructura de Active Directory
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48276564
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de infraestructura de Active Directory para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Antes de iniciar el proceso de preparación de Servicios de dominio de Active Directory para Lync Server 2013, asegúrese de que la infraestructura de Active Directory cumpla los requisitos previos siguientes:

  - Todos los controladores de dominio (que incluyen todos los servidores de catálogo global) del bosque donde implementa Lync Server ejecutan uno de los siguientes sistemas operativos:
    
      - Sistema operativo de Windows Server 2012 R2
    
      - Sistema operativo de Windows Server 2012
    
      - Sistema operativo Windows Server 2008 R2
    
      - Sistema operativo Windows Server 2008
    
      - Windows Server 2008 Enterprise de 32 bits
    
      - Versiones de 32 bits o 64 bits de Sistema operativo Windows Server 2003 R2
    
      - Versiones de 32 bits o 64 bits de Sistema operativo Windows Server 2003

  - Todos los dominios en los que implemente Lync Server se elevan a un nivel funcional de dominio de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o al menos Windows Server 2003.

  - El bosque en el que implemente Lync Server se eleva a un nivel funcional de bosque de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o al menos Windows Server 2003.
    

    > [!NOTE]
    > Para cambiar el nivel funcional de dominio o bosque, vea "Aumentar los niveles funcionales de dominios y bosques" en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=263775">http://go.microsoft.com/fwlink/?linkid=263775</A>.



  - Un catálogo global se implementa en los dominios donde implementa equipos o usuarios de Lync Server.

Lync Server 2013 admite los grupos universales en los sistemas operativos Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 y Windows Server 2003. Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque. La compatibilidad de grupo universal, combinada con la delegación de administrador, simplifica la administración de una implementación de Lync Server. Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos.

