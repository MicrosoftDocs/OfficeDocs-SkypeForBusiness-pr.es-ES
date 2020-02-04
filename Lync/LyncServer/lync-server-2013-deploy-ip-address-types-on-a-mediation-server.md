---
title: 'Lync Server 2013: Implementar tipos de dirección IP en un servidor de mediación'
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
ms.openlocfilehash: ab30a2153dc7dbf5a15557f6eeaf3b6cb65f68f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Implementar tipos de dirección IP en un servidor de mediación para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-28_

Con el generador de topologías, siga los pasos que se indican en el siguiente procedimiento para implementar tipos de direcciones IP en un servidor de mediación.

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Para implementar tipos de direcciones IP en un servidor de mediación

  - En el generador de topologías, en **grupos de mediación**, haga clic con el botón secundario en el servidor de un grupo y seleccione **Editar propiedades**. (También puede seleccionar el servidor y, a continuación, hacer clic en **Editar propiedades** en el menú **acción** ).

  - En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.
    
    **Cuadro de diálogo Editar propiedades para el grupo Servidor de mediación**
    
    ![Página de propiedades generales de Lync Server con FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Página de propiedades generales de Lync Server con FQDN")
    
      - **Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.
        
        <div>
        

        > [!NOTE]  
        > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).

        
        </div>
    
      - **Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la dirección IP principal.
    
      - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.
    
      - **Dirección IP de RTC**. Definir una dirección IP de RTC cuando un servidor de mediación es independiente. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.
        
        <div>
        

        > [!NOTE]  
        > La instalación de tarjetas de interfaz de red (NIC) adicionales para admitir la configuración de la dirección IP de RTC para Lync Server 2013 no es compatible con los roles del servidor de mediación. Para obtener más información sobre las configuraciones de NIC compatibles para Lync Server 2013, consulte <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync server 2013</A>.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

