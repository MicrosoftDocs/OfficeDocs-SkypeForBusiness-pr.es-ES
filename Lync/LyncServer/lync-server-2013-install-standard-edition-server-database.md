---
title: "Lync Server 2013 : Install. de la base de données de serveur Standard Edition"
TOCTitle: Instalar la base de datos del servidor Standard Edition
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48274404
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar la base de datos del servidor Standard Edition en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-01_

La configuración de Servidor Standard Edition como único servidor de la infraestructura que alberga a usuarios se diferencia de otras instalaciones de servidores en que existe una selección específica en el **Asistente para la implementación** para configurar el servidor inicial.

## Para instalar un servidor Standard Edition

1.  Inicie sesión en el servidor en el que va a instalar Servidor Standard Edition como administrador local o dominio equivalente.

2.  Si no ha preparado Servicios de dominio de Active Directory, lleve a cabo primero esos procedimientos. Para obtener más información, consulte [Preparar Servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  En la Asistente para la implementación de Lync Server, haga clic en **Preparar el primer servidor Standard Edition**.

4.  En la página **Preparar un solo servidor Standard Edition**, haga clic en **Siguiente**.

5.  En la página **Ejecutar comandos**, se instala SQL Server 2012 Express como Almacén de administración central. Se crean las reglas de firewall necesarias. Cuando finalice la instalación de la base de datos y el software necesario como requisito previo, haga clic en **Finalizar**.
    

    > [!NOTE]
    > Es posible que la instalación inicial necesite bastante tiempo antes de mostrar actualizaciones en la pantalla de resumen de resultados de comandos. Esto se debe a la instalación de SQL Server Express. Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para hacerlo.



6.  En la página del Asistente para la implementación de Lync Server, haga clic en **Instalar Topology Builder** si no ha instalado anteriormente las herramientas administrativas. Para obtener más información, consulte [Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Confirme que hay marcas de verificación verdes junto a “Preparar Active Directory,” “Preparar el primer servidor Standard Edition” e “Instalar Topology Builder”.

