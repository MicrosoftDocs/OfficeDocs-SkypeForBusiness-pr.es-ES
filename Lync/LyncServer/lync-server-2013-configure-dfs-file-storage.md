---
title: 'Lync Server 2013: Configurar el almacenamiento de archivos'
TOCTitle: Configurar el almacenamiento de archivos
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48276287
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el almacenamiento de archivos para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013 es compatible con el uso compartido de archivos en el Sistema de archivos distribuido (DFS). Para obtener más información sobre DFS para Windows Server 2008, consulte la Guía paso a paso de los sistemas de archivos distribuidos en Windows Server 2008, en [http://go.microsoft.com/fwlink/?linkid=202835\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=202835%26clcid=0xc0a). Para usar un DFS, Lync Server 2013 requiere lo siguiente:

  - Los espacios de nombres se basan en dominios

  - Todos los servidores de espacios de nombres ejecutan Windows 2008 o posterior

La configuración de Lync Server 2013 requiere que los permisos en carpeta compartida permitan el acceso completo al Administrador. Lync Server 2013 usará a continuación permisos de archivo NTFS para las carpetas. Los permisos de recurso compartido DFS heredados no se usarán para restringir el acceso.

Para obtener más información sobre uso compartido de archivos, consulte [Compatibilidad con el almacenamiento de archivos en Lync Server 2013](lync-server-2013-file-storage-support.md) en la documentación sobre compatibilidad.

En el siguiente procedimiento se describe cómo configurar correctamente los permisos de carpeta compartida usando el Asistente de espacios de nombres DFS (como se describe en la guía de configuración de DFS).

## Procedimiento para configurar los permisos de carpeta compartida

1.  Haga clic en **Inicio** , señale **Todos los programas** , **Herramientas administrativas** y, a continuación, haga clic en **Administración de DFS** .

2.  En el árbol de consola del complemento Administración de DFS, haga clic con el botón secundario en el servidor de espacios de nombres (por ejemplo, filesrv1.contoso.com) y haga clic en **Editar configuración** .

3.  Seleccione **Permisos de carpeta compartida** .

4.  Seleccione **Usar permisos personalizados** .

5.  Para el grupo Administrador, seleccione lo siguiente en **Permitir** :
    
      - **Control completo**
    
      - **Cambiar**
    
      - **Lectura**

6.  Haga clic en **Aplicar** y en **Aceptar** .

