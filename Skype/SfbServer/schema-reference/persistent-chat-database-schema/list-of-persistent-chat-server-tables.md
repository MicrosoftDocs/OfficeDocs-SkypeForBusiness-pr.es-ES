---
title: Lista de tablas de servidores de chat persistente
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: El esquema de base de datos persistente Chat consta de las siguientes tablas.
ms.openlocfilehash: d9a00095cb18e63cc29e16ae66e608127afad606
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-tables"></a>Lista de tablas de servidores de chat persistente
 
El esquema de base de datos persistente Chat consta de las siguientes tablas.
  
## <a name="active-directory-sync"></a>Sincronización de Active Directory

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contiene las cookies de sincronización de protocolo ligero de acceso a directorios (LDAP) actuales. Cada fila corresponde a un dominio de servicios de dominio de Active Directory que supervisa activamente el servidor de charla persistente para cambios. (Los dominios de Active Directory que son relevantes para el servidor de Chat persistentes se representan en esta tabla).  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contiene cambios de pertenencia a grupo (agregar y quitar a miembros) que aún no se han procesado los pasos posteriores de sincronización de Active Directory y es una de las tablas temporales (junto con la tabla de tblADUpdates) que se utiliza en el primer paso de sincronización de Active Directory.  <br/> Los cambios de pertenencia se almacenan, procesan, o ambas, sólo para los grupos que aparecen en la tabla de tblPrincipal o que ya tienen miembros en la lista.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contiene cambios en los servicios de dominio de Active Directory que aún no se han procesado los pasos posteriores de sincronización de Active Directory y es una de las tablas temporales (junto con la tabla tblPrincipalMemberDifference) que se utiliza en el primer paso de Active Directory Sincronización.  <br/> Cambios en Active Directory se almacenan, procesan, o ambos sólo para entidades que ya figuran en la tabla tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contiene pertenencias a principales.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contiene a los principales que tienen que actualizarse desde Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contiene afiliaciones que no se pudieran actualizar por algún motivo, normalmente debido a errores de acceso a Active Directory.  <br/> Esta tabla es sólo con fines informativos. Su contenido no se utiliza.  <br/> Los principales de afiliaciones que no se pudieran actualizar correctamente se mantienen en la tabla tblPrincipalMeta y se dan otra oportunidad para actualizarse.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Los directores, afiliaciones, nodos, ámbitos y funciones

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contiene tipos principales para clasificar lo que está en la tabla tblPrincipal. Esta tabla es estática. Se configura durante la creación de la base de datos y no cambia.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contiene a todas las identidades (usuarios, carpetas, grupos etc.). Servidor de charla persistente se trata como una lista plana heterogénea. Varias columnas se basan en el tipo de cada identidad.  <br/> La mayoría de estas entidades son copias almacenadas en caché de objetos almacenados en Active Directory. Creación de la copia en caché en el Principal se denomina aprovisionamiento tabla de estos objetos de Active Directory.  <br/> Algunas entidades se crean más agresiva que otros y algunos objetos de Active Directory se omiten por completo.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contiene las afiliaciones principales que describen las pertenencias a grupos de seguridad de Active Directory y los contenedores de Active Directory.  <br/> |
|[tblNode](tblnode.md) <br/> |Contiene el nodo de categoría, como gestionado en el panel de control.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contiene los tipos de funciones y sus permisos asociados conjuntos. Esta tabla de búsqueda es estática.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contiene ámbitos asignados a los nodos.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contiene los roles asignados a los nodos.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contiene los complementos registrados que pueden asociarse con nodos.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contiene sólo el codificado "Visibilidad" y "Comportamiento" atributos que se utilizan en la tabla tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contiene los valores de los atributos codificados "Visibilidad" y "Comportamiento" que se utilizan en la tabla tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Invitaciones, Chats y otros servicios de asistencia cliente

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contiene invitaciones para todos los usuarios configurados en el sistema para todos los nodos con Auto invitar a habilitado.  <br/> |
|[tblChat](tblchat.md) <br/> |Contiene todos los mensajes de charla.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contiene el último ID de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contiene el último ID de charla que se ha generado (y utilizado en la tabla tblChat) para cada usuario.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contiene las preferencias del cliente usuario (utilizadas por los clientes heredados sólo).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contiene símbolos temporales para fines de transferencia de archivos. Cada vez que un archivo se ha cargado o descargado, el servicio de charla persistente genera un token que utiliza el cliente para tener acceso al almacén de archivos del servicio Web.  <br/> |
   
## <a name="server-support"></a>Compatibilidad con servidores

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contiene los servidores activos en el grupo de servidor de charla persistente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contiene el bloqueo del administrador para ejecutar algunos comandos de administrador. La entrada de la revisión de sistema en la tabla tblSystemRevision se incrementa después de cada publicación del bloqueo.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contiene la entrada de número de revisión utilizada (junto con la tabla de tblAdminLock) para mantener la coherencia entre varios servidores.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contiene conexiones peer-to-peer actuales entre los servicios de Chat persistentes.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contiene la configuración persistente Chat Server no compatible.  <br/> |
   

