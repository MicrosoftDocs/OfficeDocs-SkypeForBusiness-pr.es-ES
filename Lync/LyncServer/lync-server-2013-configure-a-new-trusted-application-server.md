---
title: Configurar un servidor de aplicaciones de confianza nuevo en Lync Server 2013
TOCTitle: Configurar un servidor de aplicaciones de confianza nuevo en Lync Server 2013
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48276283
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar un servidor de aplicaciones de confianza nuevo en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Una aplicación de confianza es una aplicación basada en el Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK en la que confía Microsoft Lync Server 2013. Para más información sobre las aplicaciones UCMA, vea “Documentación del SDK básico de la API administrada 3.0 de comunicaciones unificadas” en [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320%26clcid=0xc0a).

Para más información sobre cómo configurar Microsoft Outlook Web Access (OWA) y Lync Server 2013, vea la documentación de Microsoft Exchange Server 2013.

Para publicar, habilitar o deshabilitar una topología correctamente al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos RTCUniversalServerAdmins y Admins. del dominio. También es posible delegar los permisos y derechos de administrador apropiados para agregar roles de servidor. Para obtener información detallada, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación referente a la implementación. Para otros cambios de configuración, únicamente se necesita ser miembro del grupo RTCUniversalServerAdmins.

## Para configurar un servidor de aplicaciones de confianza

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

3.  Seleccione **Descargar topología de la implementación existente** y haga clic en **Aceptar**.

4.  En el cuadro de diálogo **Guardar topología como**, haga clic en el archivo de Generador de topologías que quiera usar y, a continuación, haga clic en **Guardar**.

5.  En el panel derecho, haga clic con el botón secundario en **Servidores de aplicaciones de confianza** y, a continuación, haga clic en **Nuevo grupo de aplicaciones de confianza**.

6.  Escriba el **FQDN del grupo de servidores** del grupo de aplicaciones de confianza, seleccione si se tratará de un servidor único o de varios servidores y haga clic en **Siguiente**.

7.  En la página **Seleccionar el próximo salto**, seleccione de la lista el Lync Server 2013Grupo de servidores front-end.

8.  Haga clic en **Finalizar**.

9.  Seleccione el nodo de la parte superior **Lync Server 2013 (Vista previa)** y, a continuación, en el panel **Acciones**, haga clic en **Publicar topología**.
    
    El **Grupo de aplicaciones de confianza** debe haberse creado y asociado correctamente con el Grupo de servidores front-end correcto.

