---
title: 'Lync Server 2013: ver actualizaciones de software para dispositivos de su organización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a969aac4559f02ee7d05f36bece84e40f65aca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Ver actualizaciones de software para dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Con Lync Server 2013, puede usar el servicio Web de actualización de dispositivos para ver y administrar las actualizaciones de software para los dispositivos de su organización. Estas actualizaciones están disponibles en archivos. cab (Cabinet) del sitio web de soporte técnico [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)de Microsoft en. Una vez que haya descargado el archivo. cab, ejecute el cmdlet **Import-CSDeviceUpdate** para importar las reglas de actualización del dispositivo desde el archivo. cab. Para obtener más información sobre el cmdlet **Import-CSDeviceUpdate** , consulte [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) en la documentación del shell de administración de Lync Server.

<div>


> [!TIP]  
> Antes de implementar una nueva actualización de su organización, compruebe que funciona correctamente en un dispositivo de prueba.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>Para ver las actualizaciones de software para los dispositivos de comunicaciones unificadas

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el sitio web de soporte [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)técnico de Microsoft, descargue el archivo. cab en una ubicación de un equipo de Lync Server 2013 (por\\ejemplo\\, C: actualizaciones UCUpdates. cab).

3.  Importe las reglas de actualización de dispositivos desde el\\archivo\\C: updates UCUpdates. cab ejecutando uno de los siguientes cmdlets:
    
      - Si el archivo. cab se encuentra en el mismo equipo que el que está ejecutando el servicio que se va a actualizar (servicio: Redmond-websvc-2), ejecute el siguiente cmdlet:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Si el archivo. cab se encuentra en un equipo diferente del que está ejecutando el servicio que se va a actualizar (servicio: Redmond-websvc-3), ejecute el siguiente cmdlet:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

5.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, en **actualización de dispositivo**.

6.  En la página **actualización de dispositivo** , haga clic en una actualización de la lista y, a continuación, siga uno de estos procedimientos:
    
      - **Cancelar una actualización pendiente.** Para evitar que la actualización seleccionada se implemente en los dispositivos de su organización, haga clic en el menú **acción** y, a continuación, haga clic en **Cancelar actualizaciones pendientes**.
    
      - **Aprobar una actualización.** Para permitir que la actualización seleccionada se implemente en los dispositivos de su organización, haga clic en el menú **acción** y, a continuación, haga clic en **aprobar**.
    
      - **Restaurar una actualización.** Para permitir que se implemente una actualización aprobada previamente en los dispositivos de su organización, haga clic en el menú **acción** y, a continuación, haga clic en **restaurar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

