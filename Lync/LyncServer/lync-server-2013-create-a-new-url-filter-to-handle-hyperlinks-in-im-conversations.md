---
title: "Crear filtro nuevo para URL para administrar hipervínculos en conversaciones de MI"
TOCTitle: "Créer un filtre URL pour gérer les liens hypert. dans des conv. de mess. Inst."
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48276731
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear un filtro nuevo para direcciones URL para administrar hipervínculos en conversaciones de mensajería instantánea

 

_**Última modificación del tema:** 2012-09-26_

Además de modificar el filtro global para direcciones URL, debe configurar filtros personalizados para direcciones URL dirigidos a sitios individuales en la implementación de Lync Server 2013. Para más información sobrel filtrado de direcciones URL, consulte [Configuración de la transferencia de archivos y el filtrado de direcciones URL para la mensajería instantánea (MI) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

## Para crear un filtro nuevo para direcciones URL

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Mensajería instantánea y presencia** y, a continuación, en **Filtro para direcciones URL**.

4.  En la página **Filtro para direcciones URL**, haga clic en **Nuevo**.

5.  En el cuadro de diálogo **Seleccionar un sitio**, haga clic en el sitio para el que desea crear un filtro para direcciones URL y, a continuación, haga clic en **Aceptar**.

6.  En el cuadro **Filtro para direcciones URL nuevo**, active la casilla **Habilitar filtro para direcciones URL** para habilitar el filtrado para direcciones URL del sitio.

7.  Para bloquear cualquier URL activa que contenga un archivo con una extensión que aparezca en **Extensiones de tipo de archivo a bloquear**, en **Editar filtro de archivo**, active la casilla **Bloquear direcciones URL con extensión de archivo**.

8.  En la lista desplegable **Prefijo de hipervínculo**, haga clic en la opción que corresponde a cómo desea administrar direcciones URL en conversaciones de mensajería instantánea.
    
    Con el cuadro **Permitir mensaje**, puede enviar un mensaje de advertencia al usuario cuando se envíen hipervínculos permitidos.

9.  Haga clic en **Confirmar**.

## Vea también

#### Tareas

[Configuración de la transferencia de archivos y el filtrado de direcciones URL para la mensajería instantánea (MI) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Crear un filtro de transferencia de archivos nuevo para un sitio específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Modificar el filtro de transferencia de archivos predeterminado](lync-server-2013-modify-the-default-file-transfer-filter.md)  

#### Conceptos

[Modificar el filtro para direcciones URL predeterminado](lync-server-2013-modify-the-default-url-filter.md)

