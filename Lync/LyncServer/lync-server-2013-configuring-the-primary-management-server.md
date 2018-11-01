---
title: Configuración del servicio de administración principal
TOCTitle: Configuración del servicio de administración principal
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48275075
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración del servicio de administración principal

 

_**Última modificación del tema:** 2016-12-08_

Para aprovechar al máximo las nuevas funciones de seguimiento de estado incluidas en Microsoft Lync Server 2013, los administradores primero deben designar un PC para que actúe como servidor principal de administración; después, en ese PC, debe instalar System Center Operations Manager 2007 R2 o System Center Operations Manager 2012. Además, debe instalar una versión admitida de SQL Server para que funcione como base de datos back-end de Operations Manager. Si usa System Center Operations Manager 2012, puede utilizar cualquiera de las versiones siguientes de SQL Server como base de datos back-end:

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

Si usa System Center Operations Manager 2007 R2, le recomendamos que instale SQL Server 2005 Service Pack 4 o SQL Server 2008 Service Pack 3. También puede usar SQL Server 2008 R2 como base de datos back-end para System Center Operations Manager 2007 R2. Vea el Apéndice 1 de esta documentación para más información sobre la configuración de SQL Server 2008 R2 para trabajar con System Center Operations Manager 2007 R2.

Al instalar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2 necesita instalar todos los componentes de ese producto, incluidos:

  - Base de datos operativa

  - Servidor

  - Consola

  - Cmdlets de Windows PowerShell

  - Consola web

  - Informes

  - Almacén de datos

Estos componentes y su instalación no se explicarán en detalle en este documento. Para más información sobre System Center Operations Manager 2007 R2, vea la documentación de Operations Manager 2007 R2 en [http://go.microsoft.com/fwlink/?linkid=257526\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=257526%26clcid=0xc0a) y la documentación de System Center Operations Manager 2012 en [http://go.microsoft.com/fwlink/?linkid=257527\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=257527%26clcid=0xc0a). Debe seguir dichas instrucciones si va a usar SQL Server 2005 o SQL Server 2008 Service Pack 1 como base de datos back-end.

Si usa System Center Operations Manager 2012, puede utilizar SQL Server 2012 como base de datos back-end. Para más información sobre SQL Server 2012, vea los Libros en pantalla de SQL Server 2012 en [http://go.microsoft.com/fwlink/?linkid=257528\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=257528%26clcid=0xc0a).

Tenga en cuenta que solo puede tener un servidor de administración principal por implementación de Lync Server. Además, aunque puede usar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, no puede ejecutar dos aplicaciones simultáneamente, debe elegir una u otra. Por ejemplo, si ejecuta System Center Operations Manager 2012, todos los agentes de System Center también deben ejecutar System Center Operations Manager 2012. No puede tener unos agentes ejecutando System Center Operations Manager 2012 y otros, System Center Operations Manager 2007 R2.

