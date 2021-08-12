---
title: Lista de tablas de servidores de chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: El esquema de base de datos de chat persistente consta de las tablas siguientes.
ms.openlocfilehash: bc7189eac8e8fbd42cdaa5786b82d5652c616a69ae3fc4fc180c189416a94468
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280943"
---
# <a name="list-of-persistent-chat-server-tables"></a>Lista de tablas de servidores de chat persistente
 
El esquema de base de datos de chat persistente consta de las tablas siguientes.
  
## <a name="active-directory-sync"></a>Sincronización de Active Directory

|**Table**|**Description**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contiene las cookies de sincronización del Protocolo ligero de acceso a directorios (LDAP). Cada fila corresponde a un dominio de Servicios de dominio de Active Directory que el servidor de chat persistente supervisa activamente para los cambios. (Solo los dominios de Active Directory relevantes para el servidor de chat persistente se representan en esta tabla).  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no han sido procesados por los pasos de sincronización de Active Directory posteriores y es una de las tablas temporales (junto con la tabla tblADUpdates) que se usa en el primer paso de Sincronización de Active Directory.  <br/> Los cambios de pertenencia se almacenan, procesan o ambos, solo para los grupos que aparecen en la tabla tblPrincipal o que ya tienen miembros enumerados allí.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contiene cambios en los Servicios de dominio de Active Directory que aún no se han procesado con los pasos de sincronización de Active Directory posteriores y es una de las tablas temporales (junto con la tabla tblPrincipalMemberDifference) que se usa en el primer paso de Sincronización de Active Directory.  <br/> Los cambios en Active Directory se almacenan, procesan o solo para entidades de seguridad que ya aparecen en la tabla tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contiene pertenencias a entidades de seguridad.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contiene las entidades de seguridad que deben actualizarse desde Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contiene afiliaciones que no se pudieron actualizar por algún motivo, normalmente debido a errores de acceso de Active Directory.  <br/> Esta tabla es solo con fines informativos. No se usa su contenido.  <br/> Las entidades de seguridad con afiliaciones que no se pudieron actualizar correctamente se mantienen en la tabla tblPrincipalMeta y se les da otra oportunidad de actualizarse.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entidades de seguridad, afiliaciones, nodos, ámbitos y roles

|**Table**|**Description**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contiene tipos de entidad de seguridad para clasificar lo que está en la tabla tblPrincipal. Esta tabla es estática. Se configura durante la creación de la base de datos y no cambia.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contiene todas las entidades de seguridad (usuarios, carpetas, grupos, entre otras). El servidor de chat persistente lo controla como una lista heterogéneo plana. Varias columnas se basan en el tipo de cada entidad de seguridad.  <br/> La mayoría de estas entidades de seguridad son copias almacenadas en caché de objetos almacenados en Active Directory. La creación de la copia almacenada en caché en la tabla Principal de estos objetos de Active Directory se denomina aprovisionamiento.  <br/> Algunas entidades de seguridad se crean de forma más agresiva que otras y algunos objetos de Active Directory se omiten por completo.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contiene afiliaciones principales que describen pertenencias a grupos de seguridad de Active Directory, contenedores de Active Directory, entre otros.  <br/> |
|[tblNode](tblnode.md) <br/> |Contiene el nodo de categoría, tal como se administra en el panel de control.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contiene tipos de roles y sus conjuntos de permisos asociados. Esta tabla de búsqueda es estática.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contiene ámbitos asignados a nodos.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contiene roles asignados a nodos.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contiene los complementos registrados que se pueden asociar a nodos.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contiene solo los atributos codificados "Visibility" y "Behavior" que se usan en la tabla tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contiene los valores de los atributos "Visibility" y "Behavior" codificados que se usan en la tabla tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Invitaciones, chats y otro soporte técnico de cliente

|**Table**|**Description**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contiene invitaciones para todos los usuarios aprovisionados en el sistema para todos los nodos con la invitación automática habilitada.  <br/> |
|[tblChat](tblchat.md) <br/> |Contiene todos los mensajes de chat.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contiene el último identificador de invitación que se generó (y se usó en la tabla tblPrincipalInvites) para cada usuario.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contiene el último identificador de chat que se generó (y se usó en la tabla tblChat) para cada usuario.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contiene preferencias de cliente de usuario (usadas solo por clientes heredados).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contiene tokens temporales para fines de transferencia de archivos. Cada vez que se carga o descarga un archivo, el servicio de chat persistente genera un token que el cliente usa para tener acceso al almacén de archivos del servicio web.  <br/> |
   
## <a name="server-support"></a>Compatibilidad con el servidor

|**Table**|**Description**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contiene los servidores activos del grupo de servidores de chat persistente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contiene el bloqueo de administrador para ejecutar algunos comandos de administrador. La entrada de revisión del sistema en la tabla tblSystemRevision se incrementa después de cada versión del bloqueo.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contiene la entrada de número de revisión usada (junto con la tabla tblAdminLock) para lograr la coherencia en varios servidores.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contiene conexiones punto a punto actuales entre servicios de chat persistente.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contiene la configuración no admitida del servidor de chat persistente.  <br/> |
   

