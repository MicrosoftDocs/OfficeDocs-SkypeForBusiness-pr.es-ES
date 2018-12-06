---
title: "Lync Server 2013 : Cond. prér. à l’activation de l’authentification Kerberos"
TOCTitle: Requisitos previos para habilitar la autenticación Kerberos
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48275072
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos previos para habilitar la autenticación Kerberos en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Antes de habilitar la autenticación Kerberos, asegúrese de que se han completado todas las tareas de configuración de requisitos previos y de preparación de la infraestructura:

  - Se ha ampliado el esquema de Active Directory para Lync Server 2013.

  - Se ha realizado la preparación del bosque de Active Directory para Lync Server 2013.

  - Se ha realizado la preparación del dominio de Active Directory para Lync Server 2013.

  - El Almacén de administración central se ha instalado correctamente y está disponible.

  - La topología se ha creado y publicado con Generador de topologías.

  - Se han definido e implementado los servidores y roles que requieren el Servicios web, como los servidores front-end, los servidores Standard Edition y los directores.

  - Se ha configurado e implementado Servicios de Internet Information Server (IIS) con los servicios de rol recomendados para admitir el Servicios web en Lync Server 2013.

Una vez satisfechos los requisitos previos, debe estarse preparado para crear una o más cuentas del Servicios web para su uso con la autenticación Kerberos en la implementación. Como mínimo, es necesario crear una cuenta de autenticación Kerberos para cada implementación. Sin embargo, puede crearse una cuenta en cada sitio para proporcionar autenticación local Kerberos en el sitio. Únicamente se puede especificar una sola cuenta de autenticación Kerberos por sitio.

