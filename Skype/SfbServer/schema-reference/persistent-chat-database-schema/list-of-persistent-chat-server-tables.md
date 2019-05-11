---
title: Lista de tablas de servidores de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: El esquema de base de datos de Chat persistente consta de las siguientes tablas.
ms.openlocfilehash: 3038c68004d516ce772e49af098d8520c5a1ce00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929829"
---
# <a name="list-of-persistent-chat-server-tables"></a>Lista de tablas de servidores de chat persistente
 
El esquema de base de datos de Chat persistente consta de las siguientes tablas.
  
## <a name="active-directory-sync"></a>Sincronización de Active Directory

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contiene las cookies de protocolo ligero de acceso a directorios (LDAP) actuales. Cada fila corresponde a un dominio de los servicios de dominio de Active Directory que supervisa activamente Persistent Chat Server para que los cambios. (Sólo los dominios de Active Directory que son relevantes para el servidor de Chat persistente se representan en esta tabla).  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contiene los cambios de pertenencia de grupo (tanto agregar y quitar a miembros) que aún no se han procesado por los pasos posteriores de sincronización de Active Directory y es una de las tablas temporales (junto con la tabla Tbladupdate) que se usa en el primer paso de sincronización de Active Directory.  <br/> Cambios de pertenencia se almacenan, procesan, o ambas, únicamente para los grupos que se enumeran en la tabla tblPrincipal o que ya tienen miembros enumerados ahí.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contiene los cambios realizados en los servicios de dominio de Active Directory que aún no se han procesado por los pasos posteriores de sincronización de Active Directory y es una de las tablas temporales (junto con la tabla tblPrincipalMemberDifference) que se usa en el primer paso de Active Directory Sincronizar.  <br/> Los cambios realizados en Active Directory se almacenan, procesan, o ambos, sólo con entidades de seguridad que ya se muestran en la tabla tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contiene pertenencias de la entidad de seguridad.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contiene las entidades de seguridad que se deben actualizar desde Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contiene las afiliaciones que no se pudieron actualizar por algún motivo, generalmente debido a errores de acceso de Active Directory.  <br/> Esta tabla es sólo con fines informativos. No se usa su contenido.  <br/> Las entidades de seguridad con afiliaciones que no se pudieron actualizar correctamente se conservan en la tabla tblPrincipalMeta y tienen otra oportunidad para actualizarse.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entidades de seguridad, afiliaciones, nodos, ámbitos y Roles

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contiene los tipos de entidad de seguridad para clasificar lo que aparece en la tabla tblPrincipal. Esta tabla es estática. Se configura durante la creación de la base de datos y no cambia.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contiene todas las entidades de seguridad (usuarios, carpetas, grupos y así sucesivamente). Servidor de Chat persistente se trata como una lista plana heterogénea. Distintas columnas se basan en el tipo de cada entidad de seguridad.  <br/> La mayoría de estas entidades de seguridad son copias almacenadas en caché de objetos almacenados en Active Directory. Creación de la copia en caché en la entidad de seguridad se denomina aprovisionamiento de tabla de estos objetos de Active Directory.  <br/> Algunas entidades principales se crean de manera más enérgica que otras personas, y algunos objetos de Active Directory se omiten por completo.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contiene las afiliaciones principales que describen pertenencias en los grupos de seguridad de Active Directory, los contenedores de Active Directory y así sucesivamente.  <br/> |
|[tblNode](tblnode.md) <br/> |Contiene el nodo de categoría, según se administra en el panel de control.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contiene tipos de rol y sus permisos asociados conjuntos. Esta tabla de búsqueda es estática.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contiene ámbitos asignados a nodos.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contiene los roles asignados a nodos.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contiene los complementos registrados que se pueden asociados con nodos.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contiene sólo los codificados de forma rígida "Visibility" y "Behavior" atributos que se usan en la tabla tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contiene los valores de los atributos "Visibility" y "Behavior" codificados de forma rígida que se usan en la tabla tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Invitaciones, Chats y compatibilidad con clientes

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contiene invitaciones para todos los usuarios en el sistema para todos los nodos con invitación automática habilitada.  <br/> |
|[tblChat](tblchat.md) <br/> |Contiene todos los mensajes de chat.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contiene el último identificador de chat generado (y utilizado en la tabla tblChat) para cada usuario.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contiene las preferencias de cliente del usuario (usadas por los clientes heredados sólo).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contiene símbolos temporales con fines de transferencia de archivo de. Cada vez que un archivo se carga o descarga, el servicio de Chat persistente genera un token que el cliente utiliza para obtener acceso al almacén de archivo del servicio Web.  <br/> |
   
## <a name="server-support"></a>Compatibilidad con servidores

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contiene los servidores activos en el grupo de servidores de Chat persistente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contiene el bloqueo de administrador para ejecutar algunos comandos de administrador. La entrada de la revisión del sistema en la tabla tblSystemRevision se incrementa después de cada versión del bloqueo.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contiene la entrada de número de revisión utilizada (junto con la tabla tblAdminLock) para mantener la coherencia entre varios servidores.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contiene las conexiones punto a punto actuales entre los servicios de Chat persistente.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contiene la configuración de servidor de Chat persistente no compatible.  <br/> |
   

