---
title: 'Lync Server 2013: Implementar tipos de direcciones IP en un servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33ab774cc5b0f15ed04d3803741b6355230130fb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a>Implementar tipos de direcciones IP en un servidor front-end para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-28_

Con el generador de topologías, siga los pasos que se indican en el siguiente procedimiento para implementar tipos de direcciones IP en un servidor front-end.

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Para implementar los tipos de direcciones IP en un servidor front-end

1.  En **Grupo de servidores front-end Enterprise Edition**, haga clic con el botón secundario dentro de un grupo y seleccione **Editar propiedades** (también puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).

2.  En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.
    
    **Cuadro de diálogo Editar propiedades para el grupo de servidores front-end**
    
    ![Cuadro de diálogo Propiedades de edición del servidor front-end] (images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Cuadro de diálogo Propiedades de edición del servidor front-end")
    
      - **Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.
        
        <div>
        

        > [!NOTE]  
        > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).

        
        </div>
    
      - **Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la **dirección IP principal**.
    
      - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.
    
      - **Dirección IP de RTC**. La instalación de tarjetas de interfaz de red (NIC) adicionales para admitir la configuración de la dirección IP de RTC para Lync Server 2013 no es compatible con los roles del servidor de mediación. Para obtener más información sobre las configuraciones de NIC compatibles para Lync Server 2013, consulte [plataformas de hardware de servidor para Lync server 2013](lync-server-2013-server-hardware-platforms.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

