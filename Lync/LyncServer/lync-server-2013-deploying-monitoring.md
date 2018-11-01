---
title: Implementación de supervisión en Lync Server 2013
TOCTitle: Implementación de supervisión en Lync Server 2013
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48274472
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de supervisión en Lync Server 2013

 

_**Última modificación del tema:** 2013-12-17_

Se han realizado cambios principales en la infraestructura de supervisión de Microsoft Lync Server 2013, comenzando por el hecho de que el rol del servidor de supervisión se ha dejado de usar. En lugar de roles de servidor de supervisión independientes (que normalmente requerían que las organizaciones configuraran equipos dedicados para que actuaran como servidores de supervisión) se instalan ahora servicios de supervisión en cada servidor front-end. Entre otras cuestiones, este cambio ayuda a:

  - Disminuir el número de roles de servidor necesarios al implementar Lync Server 2013. En este caso, al dejar de usar el servidor de supervisión también se contribuye a reducir costes eliminando la necesidad de mantener servidores dedicados para supervisión.

  - Reduzca la complejidad de la instalación y la administración de Lync Server. Al instalar automáticamente los servicios de supervisión en cada servidor front-end ya no tiene que instalar, configurar y administrar el rol del servidor de supervisión.


> [!NOTE]
> El rol del servidor de archivado también se ha dejado de usar en Lync Server 2013. Como los servicios de supervisión, los servicios de archivado de Lync Server 2013 se instalan ahora en cada servidor front-end. Esto es importante tenerlo en cuenta simplemente porque la supervisión y el archivado a menudo comparten la misma instancia de base de datos de SQL Server.



Como puede esperar, estos cambios tienen un impacto principal en la manera en que se instalan y se administran los servicios de supervisión. Por ejemplo, debido a que el rol del servidor de supervisión ya no existe, el nodo del servidor de supervisión se ha eliminado del Generador de topologías de Lync Server; a su vez, eso significa que ya no se usa el asistente para nuevo servidor de supervisión del Generador de topologías para agregar un nuevo servidor de supervisión a la topología. (Ese asistente ya no existe.) En su lugar, normalmente se implementarán servicios de supervisión dentro de la topología completando los siguientes dos pasos:

1.  Habilitando la supervisión al mismo tiempo que configura un nuevo grupo de servidores de Lync Server. (En Lync Server 2013, la supervisión está habilitada o deshabilitada según cada grupo de servidores.) Tenga en cuenta que puede habilitar la supervisión para un grupo de servidores sin recopilar realmente datos de supervisión, un proceso explicado en la sección de configuración de grabación de detalles de llamada y valores de calidad de experiencia de esta documentación.

2.  Asociando un almacén de supervisión (es decir, una base de datos de supervisión) con el nuevo grupo de servidores. Tenga en cuenta que un único almacén de supervisión se puede asociar con varios grupos de servidores. En función del número de usuarios hospedados en sus grupos de servidores del registrador, eso significa que no tiene que configurar una base de datos de supervisión independiente para cada uno de sus grupos de servidores. En su lugar, el almacén de supervisión único se puede usar por varios grupos de servidores.

Aunque a menudo es más sencillo habilitar la supervisión al mismo tiempo que crea un nuevo grupo de servidores, también es posible crear un nuevo grupo de servidores con la supervisión deshabilitada. Si lo hace, posteriormente podrá usar el Generador de topología para habilitar el servicio: el Generador de topologías ofrece una manera de habilitar o deshabilitar la supervisión para un grupo de servidores, o para asociar un grupo de servidores con un almacén de supervisión diferente. Tenga en cuenta que aunque ya no hay un rol de servidor de supervisión, todavía tendrá que crear uno o más almacenes de supervisión: bases de datos back-end usadas para almacenar los datos recopilados por el servicio de supervisión. Estas bases de datos back-end se pueden crear con Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012.


> [!NOTE]
> Si se ha habilitado la supervisión para un grupo de servidores puede deshabilitar el proceso de recopilación de datos de supervisión sin tener que cambiar la topología: Shell de administración de Lync Server le ofrece una manera de deshabilitar (y posteriormente volver a habilitar) el registro de detalles de llamada (CDR) o la recopilación de datos de calidad de experiencia (QoE). Para obtener más información, vea la sección de configuración del registro de detalles de llamadas y los valores de calidad de experiencia de este documento.



Otra importante mejora para la supervisión en Lync Server 2013 es el hecho de que los informes de supervisión de Lync Server admiten ahora IPv6: los informes que usan el campo Dirección IP mostrarán las direcciones IPv4 o IPv6 en función de: 1) la consulta SQL que se está usando; y, 2) dónde o no se almacena la dirección IPv6 en la base de datos de supervisión.


> [!NOTE]
> Asegúrese de que el tipo de inicio del servicio del agente de SQL Server sea Automático y de que el servicio del agente de SQL Server se esté ejecutando para la Instancia SQL que contiene las bases de datos de supervisión, de manera que las tareas de mantenimiento predeterminadas de SQL Server de supervisión puedan ejecutarse según se programaron, bajo el control del servicio agente SQL Server.



Esta documentación le guía por el proceso de instalación y configuración de la supervisión y los informes de supervisión para Lync Server 2013. La documentación proporciona instrucciones detalladas que le ayudarán a:

  - Habilitar la supervisión en su topología y asociar un almacén de supervisión a un grupo de servidores front-end.

  - Instalar SQL Server Reporting Services y los informes de supervisión de Lync Server. Los informes de supervisión son informes preconfigurados que ofrecen diferentes vistas sobre la información almacenada en una base de datos de supervisión.

  - Configure el registro de detalles de llamada (CDR) y la recopilación de datos de calidad de experiencia (QoE). El registro de detalles de llamada le ofrece una manera de realizar un seguimiento del uso de las capacidades de Lync Server como llamadas telefónicas de voz sobre IP (VoIP); mensajería instantánea (MI); transferencias de archivo; conferencia de audio/vídeo (A/V); y sesiones de uso compartido de aplicación. Las métricas QoE controlan la calidad de las llamadas de audio y vídeo de la organización, incluyen datos sobre el número de paquetes perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

  - Depure manualmente los registros de CDR y/o QoE de la base de datos de supervisión.

