---
title: Habilitar y deshabilitar la integración con Exchange Storage
TOCTitle: Habilitar y deshabilitar la integración con Exchange Storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48276559
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar y deshabilitar la integración con Exchange Storage

 

_**Última modificación del tema:** 2012-10-09_

En Panel de control de Lync Server 2013 se usan las configuraciones de archivado para habilitar y deshabilitar la integración con el almacenamiento de Exchange. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Configuraciones opcionales de nivel de sitio o de grupo que se pueden crear y usar para especificar cómo se implementa el archivado para sitios o grupos específicos.

Para más información sobre cómo implementar las configuraciones de archivado, incluidas las opciones que se pueden especificar y la jerarquía de estas configuraciones, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planificación, implementación u operaciones.

## Para habilitar o deshabilitar la integración con el almacenamiento de Microsoft Exchange:

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:
    
      - Para habilitar la integración con el almacenamiento de Exchange 2013, active la casilla **Integración de Microsoft Exchange**.
    
      - Para deshabilitar la integración con el almacenamiento de Exchange 2013, desactive la casilla **Integración de Microsoft Exchange**.

5.  Haga clic en **Confirmar**.

## Vea también

#### Conceptos

[Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Otros recursos

[Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

