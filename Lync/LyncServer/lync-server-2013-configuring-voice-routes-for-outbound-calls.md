---
title: "Lync Server 2013 : Conf. des itinéraires de comm. voc. pour appels sortants"
TOCTitle: Configuración de rutas de voz para llamada salientes
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48275024
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de rutas de voz para llamadas salientes en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Una ruta de voz de Lync Server 2013 asocia números de teléfono de destino con uno o más troncos SIP y puertas de enlace de red telefónica conmutada (RTC) y con uno o más registros de uso RTC.

**Para ver las rutas de voz usando el Panel de control de Lync Server**

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Haga clic en **Enrutamiento de voz**.

3.  Haga clic en **Ruta**.

4.  Haga doble clic en una ruta de voz para ver otras propiedades de la lista de rutas de voz o seleccione la ruta y haga clic en **Editar**. A continuación, haga clic en **Mostrar detalles**.
    

    > [!NOTE]
    > Solamente puede ver información detallada para una única ruta a la vez.



**Para ver las rutas de voz usando el Windows PowerShell**

  - Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.Las rutas de voz pueden visualizarse utilizando Windows PowerShell y el cmdlet **Get-CsVoiceRoute**. Este cmdlet puede ejecutarse desde el Shell de administración de Lync Server 2013 o bien desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Para ver información sobre todas sus rutas de voz, escriba el siguiente comando en el Shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsVoiceRoute
    
    Devolverá información similar a la siguiente:
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :


> [!NOTE]
> Para obtener más información, consulte <A href="lync-server-2013-voice-routes.md">Rutas de voz en Lync Server 2013</A> en la documentación sobre planeamiento.



## En esta sección

  - [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md)

  - [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md)

## Vea también

#### Otros recursos

[Administrar el enrutamiento de voz en Lync Server 2013](lync-server-2013-managing-voice-routing.md)

