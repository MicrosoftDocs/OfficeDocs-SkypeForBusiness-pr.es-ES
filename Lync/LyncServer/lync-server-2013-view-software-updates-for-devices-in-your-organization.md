---
title: "Afficher des màj logicielles pour les périphériques dans Lync Server 2013"
TOCTitle: "Afficher des màj logicielles pour les périphériques dans Lync Server 2013"
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48276771
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver actualizaciones de software para dispositivos en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Con Lync Server 2013, se usa Servicio web de actualización de dispositivos para ver y administrar las actualizaciones de software para los dispositivos de la organización. Estas actualizaciones se encuentran disponibles en archivos .cab en el sitio web de soporte de Microsoft en [http://go.microsoft.com/fwlink/?linkid=204091\&clcid=0xc0a](http://go.microsoft.com/fwlink/?linkid=204091%26clcid=0xc0a). Una vez que haya descargado el archivo .cab, ejecute el cmdlet **Import-CSdeviceUpdate** para importar las reglas de actualización de dispositivos desde el archivo .cab. Para obtener información detallada sobre el cmdlet **Import-CSdeviceUpdate**, consulte [Import-CsDeviceUpdate](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsDeviceUpdate) en la documentación de Shell de administración de Lync Server.

> [!TIP]  
> Antes de implementar una actualización nueva para la organización, compruebe que funciona correctamente en un dispositivo de pruebas.



## Para ver actualizaciones de software para dispositivos de comunicaciones unificadas

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Desde el sitio web de soporte de Microsoft en [http://go.microsoft.com/fwlink/?linkid=204091\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=204091%26clcid=0xc0a), descargue el archivo .cab en una ubicación en un equipo con Lync Server 2013 (por ejemplo, C:\\Actualizaciones\\UCUpdates.cab).

3.  Importe las reglas de actualización de dispositivos desde el archivo C:\\Updates\\UCUpdates.cab; para ello, ejecute uno de los cmdlets siguientes:
    
      - Si el archivo .cab se encuentra en el mismo equipo que el que ejecuta el servicio a actualizar (service:Redmond-websvc-2), ejecute el cmdlet siguiente:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Si el archivo .cab se encuentra en un equipo diferente al que ejecuta el servicio a actualizar (service:Redmond-websvc-3), ejecute el cmdlet siguiente:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

5.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Actualización de dispositivos**.

6.  En la página **Actualización de dispositivos**, haga clic en una actualización de la lista y, a continuación, siga uno de los procedimientos a continuación:
    
      - **Cancelar una actualización pendiente.** Para impedir que se implemente la actualización seleccionada en los dispositivos de la organización, haga clic en el menú **Acción** y, a continuación, haga clic en **Cancelar actualizaciones pendientes**.
    
      - **Aprobar y actualizar.** Para permitir que se implemente la actualización seleccionada en los dispositivos de la organización, haga clic en el menú **Acción** y, a continuación, en **Aprobar**.
    
      - **Restaurar y actualizar.** Para permitir que se implemente una actualización anteriormente aprobada en los dispositivos de la organización, haga clic en el menú **Acción** y, a continuación, en **Restaurar**.

## Vea también

#### Otros recursos

[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

