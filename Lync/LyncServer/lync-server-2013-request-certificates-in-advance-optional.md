---
title: 'Lync Server 2013: Solicitar los certificados con anterioridad (opcional)'
TOCTitle: Solicitar los certificados con anterioridad (opcional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48276226
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Solicitar los certificados con anterioridad (opcional) para Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Los certificados son necesarios para todos los servidores internos que ejecutan Lync Server 2013, incluyendo cada Servidor front-end de Enterprise Edition, Servidor Standard Edition, Director, Servidor perimetral y Servidor de mediación independiente. Aunque para los servidores internos se recomienda una entidad de certificación (CA) empresarial interna, también puede usar una pública. Para obtener más información sobre los requisitos de certificado y sobre el uso de una CA pública, vea [Requisitos de certificado para Servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación sobre planeamiento.

La instalación de Lync Server 2013 incluye el Asistente para certificados que facilita las tareas de solicitud, asignación e instalación de certificados durante la implementación. Si desea solicitar certificados antes de instalar los servidores (por ejemplo, para ahorrar tiempo durante la implementación real de los servidores), puede hacerlo usando un equipo donde estén instaladas las herramientas administrativas de Lync Server 2013 o mediante un procedimiento de solicitud de certificado que esté definido en su organización, siempre que se asegure de que los certificados se puedan exportar y contengan todos los nombres alternativos del sujeto. Solicitar los certificados por adelante es opcional. Si no los solicita por adelantado, deberá solicitarlos durante el proceso de instalación de cada servidor que necesite un certificado.

Esta documentación referente a la implementación proporciona procedimientos para usar el Asistente para certificados para solicitar certificados durante el proceso de instalación, tal y como se describe en las secciones [Configurar certificados para servidores en Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configurar los certificados para el director en Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) y [Instalar los archivos del servidor de mediación en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) de la documentación referente a la implementación. Si solicita certificados por adelantado, deberá modificar los procedimientos de implementación de certificados en estas secciones según convenga para importar y asignar los certificados, en lugar de solicitarlos durante la implementación.


> [!NOTE]
> Lync Server 2013 es compatible con certificados SHA-256 para conexiones de clientes que ejecuten los sistemas operativos Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2 y Windows 7, así como Lync Phone Edition. Para permitir el acceso externo mediante SHA-256, el certificado externo lo emite una CA pública que usa SHA-256.


