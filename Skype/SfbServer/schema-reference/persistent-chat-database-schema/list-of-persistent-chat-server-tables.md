---
title: Lista de tablas de servidores de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: El esquema de base de datos de chat persistente consta de las siguientes tablas.
ms.openlocfilehash: 6a6c0bc2c2cc2d5e5ba59f9f636ed9cea2189bed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295653"
---
# <a name="list-of-persistent-chat-server-tables"></a>Lista de tablas de servidores de chat persistente
 
El esquema de base de datos de chat persistente consta de las siguientes tablas.
  
## <a name="active-directory-sync"></a>Sincronización de Active Directory

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contiene las cookies de sincronización del Protocolo ligero de acceso a directorios (LDAP). Cada fila corresponde a un dominio de servicios de dominio de Active Directory en el que el servidor de chat persistente está supervisando activamente los cambios. (En esta tabla solo se representan los dominios de Active Directory pertinentes para el servidor de chat persistente).  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contiene cambios en la pertenencia a grupos (miembros agregados y eliminados) que aún no han sido procesados por los pasos de sincronización de Active Directory más recientes y es una de las tablas temporales (junto con la tabla tblADUpdates) que se usa en el primer paso de la sincronización de Active Directory.  <br/> Los cambios de pertenencia se almacenan, se procesan o ambos, solo para los grupos que se muestran en la tabla tblPrincipal o que ya tienen miembros.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contiene cambios en los servicios de dominio de Active Directory que aún no han sido procesados por los pasos de sincronización de Active Directory más recientes y es una de las tablas temporales (junto con la tabla tblPrincipalMemberDifference) que se usa en el primer paso de Active Directory. Sync.  <br/> Los cambios en Active Directory se almacenan, se procesan o ambos solo para los principales que ya aparecen en la tabla tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contiene pertenencias principales.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contiene las entidades de identidad que deben actualizarse desde Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contiene afiliaciones que no se pudieron actualizar por alguna razón, generalmente debido a errores de acceso a Active Directory.  <br/> Esta tabla es solo para fines informativos. No se utiliza su contenido.  <br/> Las principales de las afiliaciones que no se hayan actualizado correctamente se guardan en la tabla tblPrincipalMeta y se les da otra oportunidad para que se actualicen.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Principales, afiliaciones, nodos, ámbitos y roles

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contiene tipos de principal para categorizar lo que hay en la tabla tblPrincipal. Esta tabla es estática. Se configura durante la creación de la base de datos y no cambia.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contiene todos los principales (usuarios, carpetas, grupos, etc.). El servidor de chat persistente gestiona esto como una lista heterogénea plana. Varias columnas se basan en el tipo de cada principal.  <br/> La mayoría de estos principios son copias almacenadas en caché de los objetos almacenados en Active Directory. La creación de la copia en caché en la tabla principal de estos objetos de Active Directory se denomina suministro.  <br/> Algunas entidades de identidad se crean de forma más agresiva que otras, y algunos objetos de Active Directory se pasan por alto.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contiene las afiliaciones principales que describen las pertenencias a grupos de seguridad de Active Directory, contenedores de Active Directory, etc.  <br/> |
|[tblNode](tblnode.md) <br/> |Contiene el nodo de categoría, administrado en el panel de control.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contiene tipos de roles y sus conjuntos de permisos asociados. Esta tabla de búsqueda es estática.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contiene ámbitos asignados a los nodos.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contiene roles asignados a nodos.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contiene los complementos registrados que se pueden asociar con nodos.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contiene solo los atributos "Visibility" y "Behavior" codificados que se usan en la tabla tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contiene los valores de los atributos "Visibility" y "Behavior" codificados que se usan en la tabla tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Invitaciones, chats y otros tipos de asistencia al cliente

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contiene invitaciones para todos los usuarios aprovisionados del sistema en todos los nodos con la opción de invitación automática habilitada.  <br/> |
|[tblChat](tblchat.md) <br/> |Contiene todos los mensajes instantáneos.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contiene el identificador de la última invitación que se generó (y se usó en la tabla tblPrincipalInvites) para cada usuario.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contiene preferencias de clientes de usuario (solo utilizadas por clientes heredados).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contiene tokens temporales para la transferencia de archivos. Cada vez que se carga o descarga un archivo, el servicio de chat persistente genera un token que el cliente usa para acceder al almacén de archivos del servicio Web.  <br/> |
   
## <a name="server-support"></a>Compatibilidad con servidores

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contiene los servidores activos del grupo de servidores de chat persistente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contiene el bloqueo de administrador para ejecutar algunos comandos de administrador. La entrada de revisión del sistema de la tabla tblSystemRevision se incrementa después de cada lanzamiento de bloqueo.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contiene la entrada del número de revisión usado (junto con la tabla tblAdminLock) para lograr la coherencia entre varios servidores.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contiene conexiones de punto a punto actuales entre servicios de chat persistente.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contiene la configuración no compatible del servidor de chat persistente.  <br/> |
   

