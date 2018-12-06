---
title: 'Lync Server 2013: Iniciar servicios en servidores'
TOCTitle: Iniciar servicios en servidores
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48277224
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Iniciar servicios en servidores para Lync Server 2013

 

_**Última modificación del tema:** 2014-09-03_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario miembro del grupo RTCUniversalServerAdmins o tener los permisos correctos delegados. Para obtener más información sobre la delegación de permisos, consulte el tema [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Después de instalar el almacén de configuración local en los servidores, instalar los componentes de Lync Server 2013 y configurar certificados en un Servidor front-endServidor front-end, debe iniciar los servicios de Lync Server 2013 en el servidor. Siga el procedimiento descrito a continuación para iniciar los servicios en cada Servidor front-end de la implementación.

## Para iniciar servicios en un servidor Standard Edition o front-end

1.  En Asistente para la implementación de Lync Server, en la página **Lync Server 2013**, haga clic en **Ejecutar**, junto a **Paso 4: Iniciar servicios**.

2.  En la página **Iniciar servicios**, haga clic en **Siguiente** para iniciar los servicios de Lync Server en el servidor.

3.  En la página **Ejecución de comandos**, una vez que todos los servicios se hayan iniciado correctamente, haga clic en **Finalizar**.
    
    > [!IMPORTANT]  
    > El comando para iniciar los servicios en el servidor es un método de &quot;mejor esfuerzo&quot; para informar de que los servicios ya se han iniciado. Es posible que no refleje el estado actual del servicio. Se recomienda llevar a cabo el paso <strong>Estado del servicio (opcional)</strong> justo después de <strong>Iniciar servicios</strong> para abrir Microsoft Management Console (MMC) y comprobar si los servicios se han iniciado correctamente. Si algún servicio de Lync Server no se ha iniciado, haga clic con el botón secundario en el servicio en cuestión en MMC y haga clic en <strong>Iniciar</strong>.
    

