---
title: Crear un filtro de transferencia de archivos nuevo para un sitio específico
TOCTitle: Crear un filtro de transferencia de archivos nuevo para un sitio específico
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48276739
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear un filtro de transferencia de archivos nuevo para un sitio específico

 

_**Última modificación del tema:** 2012-10-18_

Además de modificar el filtro global de transferencia de archivos, debe configurar filtros personalizados de transferencia de archivos para los sitios específicos en la implementación de Lync Server 2013. Para más información sobrel filtrado de transferencia de archivos, consulte [Configuración de la transferencia de archivos y el filtrado de direcciones URL para la mensajería instantánea (MI) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

## Para crear un filtro de transferencia de archivos para un sitio específico

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Mensajería instantánea y presencia** y, a continuación, en **Filtro de archivo**.

4.  En la página **Filtro de archivo**, haga clic en **Nuevo**.

5.  En el cuadro de diálogo **Seleccionar un sitio**, haga clic en el sitio para el que desea crear un filtro de transferencia de archivos y, a continuación, haga clic en **Aceptar**.

6.  En **Nuevo filtro de archivo**, haga clic en la casilla **Habilitar filtro de archivos**.

7.  En la lista desplegable **Transferencia de archivos**, haga clic en **Bloquear todos** o en **Bloquear tipos de archivos específicos**.

8.  Si hizo clic en **Bloquear todos**, vaya al paso 9.

9.  Si hizo clic en **Bloquear tipos de archivos específicos**, haga lo siguiente:
    
    1.  Haga clic en **Seleccionar** para modificar la lista predeterminada de las extensiones de tipo de archivo que desea bloquear.
    
    2.  En el cuadro de diálogo **Seleccionar tipo de archivo**, seleccione los tipos de archivo que desea bloquear o permitir; para ello permita o quite sus extensiones de las categorías en **Extensiones de tipo de archivo**.
    
    3.  Si no ve la extensión para un tipo de archivo que desea bloquear, escriba la extensión en el cuadro de texto en **Agregar extensiones de tipo de archivo a la lista** y, a continuación, haga clic en **Agregar**.
    
    4.  Haga clic en **Aceptar**.

10. Haga clic en **Confirmar**.

## Vea también

#### Tareas

[Configuración de la transferencia de archivos y el filtrado de direcciones URL para la mensajería instantánea (MI) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Crear un filtro nuevo para direcciones URL para administrar hipervínculos en conversaciones de mensajería instantánea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Modificar el filtro de transferencia de archivos predeterminado](lync-server-2013-modify-the-default-file-transfer-filter.md)  

#### Conceptos

[Modificar el filtro para direcciones URL predeterminado](lync-server-2013-modify-the-default-url-filter.md)

