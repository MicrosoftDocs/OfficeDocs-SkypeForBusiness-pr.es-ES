---
title: Proceso de migración - Detalles
TOCTitle: Proceso de migración - Detalles
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48276665
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proceso de migración - Detalles

 

_**Última modificación del tema:** 2016-12-08_

Use los siguientes requisitos previos y pasos detallados para migrar Lync Server 2010, chat en grupo o Chat en grupo de Office Communications Server 2007 R2 a Servidor de chat persistente de Lync Server 2013.

## Requisitos previos de migración

Compruebe que cumple los siguientes requisitos previos antes de migrar Lync Server 2010, chat en grupo o Chat en grupo de Office Communications Server 2007 R2 a Servidor de chat persistente de Lync Server 2013.

1.  Implemente al menos un grupo de Lync Server 2013. Si tiene varios grupos de Lync Server 2013, decida qué grupo de Lync Server 2013 hospedará el nuevo Grupo de servidores de chat persistente de Lync Server 2013.

2.  Instale Grupo de servidores de chat persistente de Lync Server 2013. Estará vacío (sin categorías, salones ni complementos). Antes de migrar a las categorías, salones o complementos heredados puede crear salones, categorías o complementos en la implementación de Servidor de chat persistente de Lync Server 2013.
    
    > [!IMPORTANT]  
    > Tenga presente que estos nuevos elementos pueden entrar en conflicto con los elementos heredados que migre. Evite los conflictos de nombres, de lo contrario se sobrescribirán cuando se migren los datos heredados.
    


## Preparar los datos de origen para la migración

Haga lo siguiente para preparar correctamente los datos de origen para la migración.

1.  Haga una copia de seguridad de las bases de datos de origen para Lync Server 2010, chat en grupo o Chat en grupo de Office Communications Server 2007 R2. Para más información sobre las copias de seguridad de SQL Server, consulte "Información general de copia de seguridad (SQL Server)" en [http://go.microsoft.com/fwlink/?linkid=254851\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=254851%26clcid=0xc0a).
    
    > [!IMPORTANT]  
    > Servicios de dominio de Active Directory debe ser el mismo. Una condición de la migración es que no se puede migrar un grupo a una implementación diferente (concretamente, a un bosque de Active Directory diferente).
    


2.  Examine la configuración de los salones de chat y las categorías de Lync Server 2010, chat en grupo o Chat en grupo de Office Communications Server 2007 R2. Herramienta de administración de chat en grupo realizará los cambios en las categorías, salones o complementos de la implementación heredada actual.
    
    > [!TIP]  
    > Los cambios en las categorías, salones o complementos de la implementación de Servidor de chat persistente de Lync Server 2013 se realizan desde Panel de control de Lync Server o a través de los cmdlets de Windows PowerShell.
    
    
    Siga estos pasos para preparar el sistema heredado para la migración.
    
    1.  Servidor de chat persistente admite categorías de un solo nivel, en lugar de un conjunto jerárquico profundo de categorías. Tras la migración, se agrega a las subcategorías el prefijo con los nombres completos de categoría principal. Puede simplificar la estructura de categorías actual conforme a sus necesidades.
    
    2.  Compruebe los **administradores** de la categoría raíz. Si existe algún administrador en este nivel, estos usuarios se agregarán como **administradores para todos los salones** tras la migración. Si su organización no requiere esto, tiene que eliminar estos administradores de la categoría raíz.
    
    3.  Compruebe la longitud de los nombres de los salones. Tras la migración, debido a que se han simplificado las estructuras de las categorías, si hay salones por debajo de una categoría secundaria, se les agregarán como prefijos los nombres completos de las categorías principales. El límite de los nombres es de 256 caracteres, incluidos los nombres de las categorías principales. Debe comprobar la longitud de los nombres de los salones y posiblemente abreviarlos, si son demasiado largos.
    
    4.  En Lync Server 2013, si la configuración de la categoría **invitaciones** es true, puede elegir true o false para las invitaciones a los salones de dicha categoría. No obstante, si se configuran las invitaciones con el valor false, los salones de esta categoría tienen las invitaciones desactivadas. Antes de la migración, debe restablecer la configuración de las invitaciones en la versión heredada de Servidor de chat en grupo de Lync Server si desea que existan salones en una categoría determinada. Si no lo hace, durante la migración, Lync Server 2013 muestra advertencias y configura los salones con el valor predeterminado de false.
    
    5.  Si ha usado archivos en los salones de chat, debe copiar manualmente con XCOPY los archivos en el nuevo almacén de archivos de Chat persistente tras la migración. Las herramientas no lo hacen.
    
    6.  Si tenía usuarios federados y salones con usuarios federados, tenga en cuenta que Servidor de chat persistente no admite la federación. Los salones con usuarios federados se migrarán, pero los propios usuarios no tendrán acceso al contenido porque no se admite el acceso federado.
    
    7.  Identifique los salones que no desea migrar y márquelos como deshabilitados.
    
    8.  Identifique la fecha a partir de la cual desea migrar el contenido de los salones de chat. Por ejemplo, quizás no desee migrar los mensajes anteriores al 1 de enero de 2010, porque ya son obsoletos o no son importantes para migrarlos.

## Realizar la migración

Haga lo siguiente para migrar Servidor de chat en grupo heredado.

1.  Cierre los servicios de Lync Server 2010, chat en grupo, Chat en grupo de Office Communications Server 2007 R2, o Servidor de chat persistente de Lync Server 2013. Deben detenerse todos los servicios. Planee, por tanto, esta acción para cuando el tiempo de inactividad sea suficientemente largo. Como se ha descrito antes, no olvide hacer una copia de seguridad de la base de datos de Chat en grupo actual.

2.  Ejecute el cmdlet Windows PowerShell**Export-CsPersistentChatData** como miembro del rol RBAC de administrador de Chat persistente (CsPersistentChatAdministrator). Para más información sobre los cmdlets de exportación e importación, consulte [Solucionar problemas de configuración de servidores de chat persistentes mediante los cmdlets de Windows PowerShell en Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Examine el contenido exportado.

3.  Antes de iniciar la importación, cierre los servicios de Servidor de chat persistente de Lync Server 2013. Deben detenerse todos los servicios. Planee, por tanto, esta acción para cuando el tiempo de inactividad sea suficientemente largo.

4.  Haga una copia de seguridad de la base de datos de Chat persistente si ha creado categorías, salones o complementos en la implementación de Lync Server 2013 antes de la migración. Aunque el proceso de exportación e importación es capaz de combinar los datos heredados con la implementación de Lync Server 2013, es conveniente realizar una copia de seguridad por si el contenido se sobrescribe accidentalmente (por ejemplo, en el caso de que se produzcan conflictos con los nombres).

5.  Ejecute el cmdlet **Import-CsPersistentChatData** de Windows PowerShell (herramienta de importación) con un comando **WhatIf** para rellenar Servidor back-end de Grupo de servidores de chat persistente con los datos migrados. En el proceso se producen algunas conversiones para acomodar el modelo de administración simplificado. Corrija los errores o las advertencias que aparezcan.

6.  Ejecute el cmdlet **Import-CsPersistentChatData** de Windows PowerShell de Servidor de chat persistente como miembro del rol RBAC de administrador de Chat persistente (CsPersistentChatAdministrator). Para más información sobre los cmdlets de exportación e importación, consulte [Solucionar problemas de configuración de servidores de chat persistentes mediante los cmdlets de Windows PowerShell en Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Debe copiar con XCOPY todos los archivos que se han cargado (toda la carpeta) en el nuevo almacén de archivos de Chat persistente de Lync Server 2013.
    
    > [!IMPORTANT]  
    > Lync 2013 (cliente) no admite la carga ni la visualización de archivos en los salones de chat. Puede seguir usando el cliente heredado para publicar y ver los archivos en el salón.
    


8.  Designe el puerto del URI del servidor de búsqueda de Lync Server 2010, chat en grupo o Chat en grupo de Office Communications Server 2007 R2 para el objeto contacto de Servidor de chat persistente de Lync Server 2013. Los pasos siguientes son necesarios si los clientes de Chat en grupo de Lync 2010 o Chat en grupo de Office Communicator 2007 R2 tienen que conectarse con la versión más reciente de Chat persistente de Lync 2013 (cliente) después de la migración sin cambios en la configuración del cliente:
    
      - Elimine la cuenta de usuario del servidor de búsqueda ocschat@ *\<nombreDeDominio\>* .com. Se usó para señalar al servicio de búsqueda en Lync Server 2010, chat en grupo. Puede desinstalar el grupo y eliminar las entradas de confianza posteriormente.
    
      - Cree un extremo heredado (objeto contacto de Servidor de chat persistente) ejecutando el cmdlet **New-CsPersistentChatEndpoint** de Windows PowerShell con el mismo URI SIP, de modo que el cliente heredado funcione correctamente cuando el servicio se reinicie.
    
    El proceso de migración obligatorio se completa en este punto. Chat en grupo de Lync 2010 (clientes) o Chat en grupo de Office Communicator 2007 R2 (clientes) pueden conectarse al nuevo Grupo de servidores de chat persistente sin problemas.
    
    Siga estos pasos para retirar la implementación de Lync Server 2010, chat en grupo o Chat en grupo de Office Communications Server 2007 R2.

9.  Inicie los servicios de Servidor de chat persistente y, para ello, encienda todos los equipos del nuevo Grupo de servidores de chat persistente.

10. Use los cmdlets de Panel de control de Lync Server y Windows PowerShell para comprobar que los datos se han migrado correctamente.

11. Desinstale Chat en grupo de Lync 2010 o Chat en grupo de Office Communicator 2007 R2 de los equipos del grupo de Servidor de chat en grupo.

12. Elimine la aplicación de confianza y el grupo de aplicaciones de confianza con los cmdlets de Windows PowerShell. Esto elimina estos elementos de Almacén de administración central y las entradas de servicio de confianza asociadas (TSE) de Active Directory. Estos pasos también funcionan con Generador de topologías (los grupos y las aplicaciones de confianza también tienen allí un nodo dedicado).

13. Ahora puede empezar a habilitar la funcionalidad de Servidor de chat persistente a través de los nuevos clientes. Para más información sobre cómo habilitar Servidor de chat persistente, consulte [Implementar el servidor de chat persistente en Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    > [!IMPORTANT]  
    > Lync Server 2013 admite varios Grupos de servidores de chat persistente. No obstante, se admite la migración de un Chat en grupo de Lync 2010 o un grupo de Chat en grupo de Office Communications Server 2007 R2 a un único Grupo de servidores de chat persistente de Lync Server 2013. Puede agregar otros Grupos de servidores de chat persistente nuevos a la implementación para cumplir los requisitos normativos (por ejemplo, la conservación de datos en una zona geográfica determinada).
    

