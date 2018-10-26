---
title: Ejecutar compatibilidad con versiones anteriores para servidor de chat persistente
TOCTitle: Ejecutar compatibilidad con versiones anteriores para servidor de chat persistente
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48275257
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ejecutar compatibilidad con versiones anteriores para servidor de chat persistente

 

_**Última modificación del tema:** 2013-02-21_

Lync Server 2013, El extremo de Servidor de chat persistente proporciona una forma de crear una sola dirección URL que señala a un Grupo de servidores de chat persistente. Es útil para clientes heredados ( Microsoft Office Communications Server 2007 R2Servidor de chat en grupo o Lync Server 2010, chat en grupo) porque los usuarios pueden escribir una sola dirección URL en la configuración manual cuando se intenta señalar el cliente heredado hacia un equipo que ejecuta Lync 2013, Chat persistente. Este extremo no lo usa el Chat persistente y es necesario solo para clientes heredados. Esto es útil para el período de transición donde pueden migrarse salones, pero los clientes de Lync 2013 no se han implementado en toda la organización. Los usuarios que ejecutan Lync 2010Chat en grupo (cliente) todavía se conectar al Servidor back-end de Servidor de chat persistente.

No debe crear varios extremos de Servidor de chat persistente; solo necesita uno para cada Grupo de servidores de chat persistente. Los administradores pueden crear varios extremos (uno por cada grupo), pero los clientes heredados solo pueden configurarse para conectarse a un grupo de servidores a la vez. En el escenario habitual o estándar, la implementación heredada es un grupo solamente. Una implementación nueva generalmente migra ese grupo a un nuevo Lync Server 2013 y podría agregar algunos nuevos Grupos de servidores de chat persistente adicionales.

Este escenario estándar generalmente sigue este patrón:

  - Los usuarios se administran con un grupo de Lync Server 2010, chat en grupo y los clientes de Chat en grupo de Lync 2010 se conectan a ese grupo mediante un usuario conocido (bien el SIP predeterminado:ocschat@ *domainName* .com o uno similar). Los usuarios son Servicios de dominio de Active Directory habilitados para SIP y el servicio de Búsqueda se registra con ellos para recibir solicitudes entrantes.

  - Posteriormente, debe instalar un Lync Server 2013Servidor de chat persistente y un Grupo de servidores de chat persistente.

  - Durante un momento en el que los usuarios suelen estar desconectados (por ejemplo, un fin de semana):
    
      - Desactive el Lync Server 2010, chat en grupo.
    
      - Migre datos del grupo de Lync Server 2010, chat en grupo al Lync Server 2013Grupo de servidores de chat persistente.
    
      - Elimine el usuario conocido del Servicios de dominio de Active Directory.
    
      - Cree un nuevo *extremo heredado* con el mismo URI de SIP que el usuario conocido eliminado previamente.
    
      - Inicie los Lync Server 2013, Servidores de chat persistente.

  - Los usuarios vuelven a iniciar sesión mediante su Chat en grupo de Lync 2010 (cliente) y se conectan a los datos sin necesidad de cambiar ninguna configuración.

  - En un momento posterior, puede retirar el Lync Server 2010, chat en grupo. Posteriormente, puede implementar el Lync Server 2013Servidor de chat persistente e instalar nuevos Lync Server 2013Grupos de servidores de chat persistente.

Para obtener detalles sobre la migración de Lync Server 2010, chat en grupo a Lync Server 2013, Servidor de chat persistente, vea [Migración del chat de grupo de Lync Server 2010 o el chat de grupo de Office Communications Server 2007 R2 al servidor de chat persistente de Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Para ejecutar la compatibilidad con versiones anteriores (para crear un extremo de Servidor de chat persistente que señale hacia un Grupo de servidores de chat persistente que puede ser utilizado por clientes heredados del grupo de servidores de Chat en grupo):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

a continuación, configure clientes de Chat persistente para usar esa dirección SIP como su objeto de contacto. La dirección SIP se crea con el cmdlet **New-CsPersistentChatEndpoint** para un Grupo de servidores de chat persistente específico.

Para agregar el extremo de Servidor de chat persistente mediante Interfaz de la línea de comandos Windows PowerShell, tenga en cuenta el siguiente ejemplo. En este caso, va a configurar el objeto de contacto para que se denomine "persistentchat" en la topología "constoso.com" donde el nombre de dominio completo (FQDN) del grupo de servidores es "pcpool.contoso.com":

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

## Vea también

#### Conceptos

[Migración del chat de grupo de Lync Server 2010 o el chat de grupo de Office Communications Server 2007 R2 al servidor de chat persistente de Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

