---
title: 'Lync Server 2013: Solicitar certificados para componentes perimetrales'
TOCTitle: Solicitar certificados para componentes perimetrales
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48275952
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Solicitar certificados para componentes perimetrales en Lync Server 2013

 

_**Última modificación del tema:** 2013-11-07_

Los certificados requeridos para admitir el acceso de usuarios externos incluyen los certificados emitidos por una entidad de certificación (CA) pública y los certificados emitidos por una CA empresarial interna:

  - Los certificados requeridos para la interfaz externa de Servidor perimetral y el proxy inverso debe emitirlos una CA pública.

  - Los certificados necesarios para la interfaz interna pueden ser emitidos por una CA pública o por una CA empresarial interna. Se recomienda el uso de una CA de Windows Server 2008, CA de Windows Server 2008 R2, CA de Windows Server 2012 o CA de Windows Server 2012 R2 internas para la creación de dichos certificados, con el fin de ahorrar los gastos que implica el uso de certificados públicos.

> [!IMPORTANT]  
> El procesamiento de las solicitudes de certificado pueden tardar, en especial las solicitudes a CA públicas, por lo que deberá solicitar los certificados para sus Servidores perimetrales con la suficiente anterioridad para que estén disponibles al iniciar la implementación de los componentes de Servidor perimetral. Para ver un resumen de los requisitos de certificado de los Servidores perimetrales, consulte <a href="lync-server-2013-certificate-requirements-for-external-user-access.md">Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013</a>.



Aunque puede optar por usar una CA pública para el certificado perimetral interno, se recomienda usar una CA empresarial interna para esos otros certificados, para minimizar el coste de los certificados. Para ver un resumen de los requisitos de certificado de los Servidores perimetrales, consulte [Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).


> [!NOTE]
> Al instalar un Servidor perimetral, la instalación incluye un asistente de certificados que facilita las tareas de solicitud, asignación e instalación de certificados, como se describe en la sección <A href="lync-server-2013-set-up-edge-certificates.md">Configurar certificados perimetrales para Lync Server 2013</A>. Si desea solicitar certificados antes de instalar un Servidor perimetral (por ejemplo, para ahorrar tiempo durante la implementación real de los componentes del Servidor perimetral), puede hacerlo usando servidores internos, asegurándose siempre de que los certificados se pueden exportar y de que contienen todos los nombres alternativos de sujeto necesarios. Esta documentación no indica los procedimientos de uso de los servidores internos para solicitar certificados.



## Solicitar certificados a una CA pública

La implementación de Servidor perimetral requiere un certificado público único para las interfaces externas de Servidores perimetrales, que se usa para Servidor perimetral de acceso, Servicio perimetral de conferencia web y para el servicio de autenticación A/V. Este certificado debe tener una clave privada exportable para garantizar que el servicio de autenticación de A/V utiliza las mismas claves en todos los Servidores perimetrales del grupo. El proxy inverso, que se utiliza con Microsoft Internet Security and Acceleration (ISA) Server 2006 o Microsoft Forefront Threat Management Gateway 2010, también requiere un certificado público.

## Solicitar certificados a una CA empresarial interna

Los certificados necesarios para la interfaz perimetral interna pueden proceder de una entidad de certificación pública o de una entidad de certificación interna. Se puede usar una entidad de certificación empresarial interna para que el costo de los certificados sea menor. Si la organización tiene implementada una entidad de certificación interna, es la que debe emitir los certificados para la red perimetral interna. Si se recurre a una entidad de certificación empresarial interna para obtener los certificados internos, el costo de los certificados se verá reducido.

Para obtener un resumen de los requisitos de certificado de los componentes perimetrales, consulte [Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Para obtener más detalles acerca del uso de una CA pública para obtener certificados, consulte [Solicitar certificados para componentes perimetrales en Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Para obtener información detallada sobre cómo solicitar, instalar y asignar certificados, consulte [Configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

