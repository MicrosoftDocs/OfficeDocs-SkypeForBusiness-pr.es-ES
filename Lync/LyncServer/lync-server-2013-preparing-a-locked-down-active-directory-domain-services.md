---
title: "Lync Server 2013 : Prép. des services de domaine Active Directory verrouillés"
TOCTitle: Preparar Servicios de dominio de Active Directory bloqueados
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48275530
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preparar Servicios de dominio de Active Directory bloqueados en Lync Server 2013

 

_**Última modificación del tema:** 2012-05-14_

Con frecuencia, las organizaciones bloquean Servicios de dominio de Active Directory para atenuar los riesgos en materia de seguridad. Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que Lync Server 2013 requiere. Preparar correctamente un entorno de Active Directory bloqueado para Lync Server 2013 implica algunas consideraciones y pasos adicionales.

A continuación se indican dos formas comunes de limitar los permisos en un entorno de Active Directory bloqueado:

  - Las entradas de control de acceso (ACE) de los usuarios autenticados se quitan de los contenedores.

  - Se deshabilita la herencia de permisos en los contenedores de los objetos User, Contact, InetOrgPerson o Computer.

## En esta sección

  - [Se quitan los permisos de usuario autenticado en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [La herencia de permisos está deshabilitada en los contenedores Computer, Users o InetOrgPerson en Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

