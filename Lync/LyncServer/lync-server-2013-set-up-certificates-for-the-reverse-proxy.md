---
title: 'Lync Server 2013: Configurar certificados para el proxy inverso'
TOCTitle: Configurar certificados para el proxy inverso
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48276542
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar certificados para el proxy inverso en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

Todos los servidores proxy inversos requieren un certificado de servidor web para usarlos en el servicio de escucha. El certificado de servidor web debe ser emitido por una entidad de certificación (CA) pública.

Para obtener información detallada sobre este y otros requisitos de certificado, consulte [Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

## Para configurar un certificado de servicios web para el servidor proxy inverso

  - Debe haber configurado previamente el servidor proxy inverso, incluida la configuración del certificado de servicios web. Si no realiza estas indicaciones antes de iniciar la implementación de los servidores perimetrales, siga los procedimientos descritos en [Configuración de los servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) para crear solicitudes e instalar el certificado de servicios web y, a continuación, crear las reglas de publicación de web y configurarlas para usar el certificado.

