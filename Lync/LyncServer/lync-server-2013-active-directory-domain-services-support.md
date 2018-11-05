---
title: 'Lync Server 2013: Compatibilidad de servicios de dominio de Active Directory'
TOCTitle: Compatibilidad de servicios de dominio de Active Directory
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48276358
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad de servicios de dominio de Active Directory en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013 usa el Almacén de administración central para almacenar datos de configuración para servidores y servicios, en lugar de basarse en Servicios de dominio de Active Directory para esta información como en versiones anteriores. Lync Server 2013 sigue almacenando en AD DS:

  - **Extensiones de esquema**
    
      - Extensiones de objetos de usuario
    
      - Extensiones de las clases de Lync Server 2010 y Office Communications Server 2007 R2 con el fin de mantener la compatibilidad con versiones anteriores.

  - **Datos** (almacenados en el esquema extendido de Lync Server 2013 y en las clases existentes)
    
      - URI de SIP del usuario y otros parámetros de usuario
    
      - Objetos de contacto de aplicaciones (por ejemplo, la Aplicación de grupo de respuesta y la Aplicación Operador de conferencia)
    
      - Datos publicados para lograr compatibilidad con versiones anteriores
    
      - Un punto de conexión de servicio (SCP) para el Almacén de administración central
    
      - Cuenta de autenticación Kerberos (un objeto de equipo opcional)

En esta sección se describen los requisitos de compatibilidad de AD DS para Lync Server 2013. Para más información sobre la compatibilidad de las topologías, consulte [Topologías admitidas de Active Directory en Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) en la documentación sobre compatibilidad.

## Sistemas operativos admitidos con los controladores de dominio

Lync Server 2013 admite los controladores de dominio que ejecutan los siguientes sistemas operativos:

  - Sistema operativo de Windows Server 2012 R2

  - Windows Server 2012nm-win-2012R2-server

  - Sistema operativo Windows Server 2008 R2

  - Sistema operativo Windows Server 2008

  - Windows Server 2008 Enterprise de 32 bits

  - Las versiones de 32 y 64 bits del sistema operativo Windows Server 2003 R2

  - Las versiones de 32 y 64 bits del sistema operativo Windows Server 2003

## Nivel funcional de bosque y dominio

Debe elevar todos los dominios en los que implemente Lync Server 2013 a un nivel funcional de dominio de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o al menos Windows Server 2003.

Todos los bosques en los que implemente Lync Server 2013 deben elevarse a un nivel funcional de bosque de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o al menos Windows Server 2003.

## Compatibilidad con los controladores de dominio de solo lectura

Lync Server 2013 admite instalaciones de Servicios de dominio de Active Directory con controladores de dominio de solo lectura o servidores de catálogo global de solo lectura, siempre y cuando haya controladores de dominio grabables.

## Nombres de dominio

Lync Server no admite dominios de etiqueta única. Por ejemplo, se admitiría un bosque con un dominio raíz denominado **contoso.local**, pero no un dominio raíz denominado **local**. Para más información, consulte el artículo 300684 de Microsoft Knowledge Base, "Información acerca de la configuración de Windows para dominios con nombres DNS de etiqueta única", en <http://go.microsoft.com/fwlink/?linkid=143752>.


> [!NOTE]
> Lync Server no admite el cambio de nombre de dominio. Si necesita cambiar el nombre de un dominio en el que esté implementado Lync Server, desinstale primero Lync Server, después cambie el nombre del dominio y por último vuelva a instalar Lync Server.



## Entornos de AD DS bloqueados

En entorno de AD DS bloqueado, los objetos de usuario y equipo se colocan a menudo en unidades organizativas (OU) específicas con la herencia de permisos deshabilitada para ayudar a proteger la delegación administrativa y para permitir al uso de objetos de directivas de grupo (GPO) para la aplicación de directivas de seguridad. Lync Server 2013 se puede implementar en un entorno de Active Directory bloqueado. Para más información sobre qué se requiere para implementar Lync Server en un entorno bloqueado, consulte [Preparar Servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) en la documentación sobre implementación.

