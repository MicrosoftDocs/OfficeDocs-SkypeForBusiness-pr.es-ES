---
title: "Configurar reglas de PIN para conferencia de acceso telefónico en Lync Server 2013"
TOCTitle: "Conf. les règles de code conf. des conférences rdv dans Lync Server 2013"
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48274722
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar reglas del número de identificación personal (PIN) de la conferencia de acceso telefónico local en Lync Server 2013

 

_**Última modificación del tema:** 2012-06-19_

Los usuarios de Lync Server 2013 que tengan credenciales de servicios de dominio de Active Directory (AD DS) en su organización pueden unirse a conferencias de acceso telefónico como usuarios autenticados mediante el uso de un número de identificación personal (PIN). La directiva de PIN define las reglas de funcionamiento de los PIN de conferencias de acceso telefónico.

Puede crear una nueva directiva de PIN si desea aplicar una directiva específica a un sitio a un grupo de usuarios determinado. Si desea usar la misma directiva de PIN para toda la organización, puede usar la directiva de PIN global y modificarla según sea necesario. Las directivas de PIN se aplican a usuarios que van del ámbito más limitado al ámbito más extenso. Si asigna una directiva de PIN de usuario a un usuario, dicha configuración tendrá preferencia. Si no asigna una directiva de usuario, se aplica la directiva de PIN de sitio, si existe. Si no se aplica ni la directiva de usuario ni la de sitio, la directiva de PIN global proporcionará la configuración predeterminada.

## En esta sección

  - [Modificar la configuración del PIN de la conferencia de acceso telefónico local predeterminada en Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [Crear o modificar la configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios en Lync Server 2013](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [Eliminar configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

