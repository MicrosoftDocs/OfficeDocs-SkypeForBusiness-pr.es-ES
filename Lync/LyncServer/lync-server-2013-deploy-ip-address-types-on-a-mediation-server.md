---
title: 'Lync Server 2013: implementar tipos de direcciones IP en un servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e7e8e897eb0bb37539284c2de5fa3dd478c28e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Implementar tipos de direcciones IP en un servidor de mediación para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-28_

Mediante el generador de topologías, lleve a cabo los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un servidor de mediación.

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Para implementar tipos de direcciones IP en un servidor de mediación

  - En el generador de topologías, en **grupos de mediación**, haga clic con el botón secundario en el servidor dentro de un grupo y, después, seleccione **Editar propiedades**. (También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).

  - En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.
    
    **Cuadro de diálogo Editar propiedades para el grupo Servidor de mediación**
    
    ![Página de propiedades generales de Lync Server con FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Página de propiedades generales de Lync Server con FQDN")
    
      - **Use todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.
        
        <div>
        

        > [!NOTE]  
        > Esta es la opción recomendada para las configuraciones de IP versión 6 (IPv6).

        
        </div>
    
      - **Limitar el uso del servicio a las direcciones especificadas**. Seleccione esta opción para especificar una dirección concreta para usarla en el nuevo servidor. Si selecciona esta opción, debe indicar un valor de dirección IP principal.
    
      - **Dirección IP principal**. Escriba una dirección IP que va a utilizar el servidor para todas las comunicaciones excepto la red telefónica conmutada (RTC) pública. La dirección IP escrita debe coincidir con el formato del tipo de dirección seleccionado.
    
      - **Dirección IP de RTC**. Definir una dirección IP RTC cuando un servidor de mediación es independiente. Esta dirección debe coincidir con el formato del tipo de dirección seleccionado.
        
        <div>
        

        > [!NOTE]  
        > La instalación de tarjetas de interfaz de red (NIC) adicionales para admitir la configuración de dirección IP de RTC para Lync Server 2013 no es compatible con roles de servidor de mediación combinados. Para obtener más información sobre las configuraciones de NIC admitidas para Lync Server 2013, vea <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync server 2013</A>.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

