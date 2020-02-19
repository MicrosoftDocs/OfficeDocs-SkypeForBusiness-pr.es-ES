---
title: 'Lync Server 2013: ver actualizaciones de software para dispositivos de la organización'
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
ms.openlocfilehash: 7926c9c10ba30ed4683b1e05d6e22c4b817f502c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Ver actualizaciones de software para dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Con Lync Server 2013, use el servicio Web de actualización de dispositivos para ver y administrar las actualizaciones de software para los dispositivos de su organización. Estas actualizaciones están disponibles en los archivos. cab (Cabinet) del sitio web de soporte [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)técnico de Microsoft en. Una vez que haya descargado el archivo. cab, ejecute el cmdlet **Import-CSDeviceUpdate** para importar las reglas de actualización de dispositivos del archivo. cab. Para obtener más información sobre el cmdlet **Import-CSDeviceUpdate** , consulte [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) en la documentación del shell de administración de Lync Server.

<div>


> [!TIP]  
> Antes de implementar una actualización nueva para la organización, compruebe que funciona correctamente en un dispositivo de pruebas.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>Para ver actualizaciones de software para dispositivos de comunicaciones unificadas

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  En el sitio web de soporte [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)técnico de Microsoft en, descargue el archivo. cab en una ubicación de un equipo de Lync Server 2013 (\\por\\ejemplo, C: actualiza UCUpdates. cab).

3.  Para importar las reglas de actualización de dispositivos del\\archivo\\C: updates UCUpdates. cab, ejecute uno de los siguientes cmdlets:
    
      - Si el archivo .cab se encuentra en el mismo equipo que el que ejecuta el servicio a actualizar (service:Redmond-websvc-2), ejecute el cmdlet siguiente:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Si el archivo .cab se encuentra en un equipo diferente al que ejecuta el servicio a actualizar (service:Redmond-websvc-3), ejecute el cmdlet siguiente:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

5.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Actualización de dispositivos**.

6.  En la página **Actualización de dispositivos**, haga clic en una actualización de la lista y, a continuación, siga uno de los procedimientos a continuación:
    
      - **Cancelar una actualización pendiente.** Para impedir que se implemente la actualización seleccionada en los dispositivos de la organización, haga clic en el menú **Acción** y, a continuación, haga clic en **Cancelar actualizaciones pendientes**.
    
      - **Aprobar y actualizar.** Para permitir que se implemente la actualización seleccionada en los dispositivos de la organización, haga clic en el menú **Acción** y, a continuación, en **Aprobar**.
    
      - **Restaurar y actualizar.** Para permitir que se implemente una actualización anteriormente aprobada en los dispositivos de la organización, haga clic en el menú **Acción** y, a continuación, en **Restaurar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Administración de dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

