---
title: Modificar el filtro de transferencia de archivos predeterminado
TOCTitle: Modificar el filtro de transferencia de archivos predeterminado
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48275748
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificar el filtro de transferencia de archivos predeterminado

 

_**Última modificación del tema:** 2012-11-01_

Lync Server 2013 proporciona un filtro de transferencia de archivos globales que bloquea tipos específicos de archivos durante las siguientes actividades relacionadas con archivos en la implementación de Lync Server 2013:

  - Solicitudes de transferencia de archivos durante conversaciones de mensajería instantánea

  - Cargas y descargas de archivos al usar la característica de documentos en el cliente de Office Live Meeting 2007

  - Reproducción multimedia durante conferencias

Según los tipos de archivos que desee bloquear o permitir, puede usar Panel de control de Lync Server para modificar el filtro global. Para obtener más información acerca del filtrado de transferencia de archivos, consulte [Configuración de la transferencia de archivos y el filtrado de direcciones URL para la mensajería instantánea (MI) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

## Para modificar el filtro de transferencia de archivos predeterminado

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Mensajería instantánea y presencia** y, a continuación, en **Filtro de archivo**.

4.  En la página **Filtro de archivo**, haga doble clic en el filtro **Global**.

5.  En **Editar filtro de archivo**, active la casilla **Habilitar filtro de archivos**.

6.  En el cuadro de lista desplegable **Transferencia de archivo**, haga clic en **Bloquear todos** o en **Bloquear tipos de archivos específicos**.

7.  Si hizo clic en **Bloquear todos**, vaya al paso 9.

8.  Si hizo clic en **Bloquear tipos de archivos específicos**, haga lo siguiente:
    
    1.  Haga clic en **Seleccionar** para modificar la lista predeterminada de las extensiones de tipo de archivo que desea bloquear.
    
    2.  En **Seleccionar tipo de archivo**, seleccione los tipos de archivo que desee bloquear o permitir agregando o quitando sus extensiones de las categorías de **Extensiones de tipo de archivo**.
    
    3.  Si no ve la extensión para un tipo de archivo que desea bloquear, escriba la extensión en el cuadro de texto en **Agregar extensiones de tipo de archivo a la lista** y, a continuación, haga clic en **Agregar**.
    
    4.  Haga clic en **Aceptar**.

9.  Haga clic en **Confirmar**.

## Vea también

#### Tareas

[Configuración de la transferencia de archivos y el filtrado de direcciones URL para la mensajería instantánea (MI) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Crear un filtro de transferencia de archivos nuevo para un sitio específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Crear un filtro nuevo para direcciones URL para administrar hipervínculos en conversaciones de mensajería instantánea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  

#### Conceptos

[Modificar el filtro para direcciones URL predeterminado](lync-server-2013-modify-the-default-url-filter.md)

