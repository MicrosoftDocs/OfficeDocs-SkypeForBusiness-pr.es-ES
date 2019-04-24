---
title: Revisar los informes del administrador en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Los informes de administrador consisten en información detallada acerca de la implementación y las operaciones. Los informes se generan en función de las elecciones realizadas en Diseñar sitios. El diseñador puede agregar más valor a los informes de administrador si se editan los diagramas de red y se definen las direcciones IP completas y los nombres de dominio completos (FQDN) de servidores, grupos y equilibradores de carga.
ms.openlocfilehash: 5cab8231428ace2a0d77132481819eed304d3519
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222740"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Review the Administrator Reports in Skype for Business Server 2015

Los informes de administrador consisten en información detallada acerca de la implementación y las operaciones. Los informes se generan en función de las elecciones realizadas en **Diseñar sitios**. El diseñador puede agregar más valor a los informes de administrador si se editan los diagramas de red y se definen las direcciones IP completas y los nombres de dominio completos (FQDN) de servidores, grupos y equilibradores de carga.

La característica de informes de administrador le permite:

- [Review the Summary Report](review-the-administrator-reports.md#Summary_report)

- [Review the Certificates Report](review-the-administrator-reports.md#Certificates_Report)

- [Review the Firewall Report](review-the-administrator-reports.md#Firewall_report)

- [Review the DNS Report](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Revisar el informe de resumen
<a name="Summary_report"> </a>

El Skype para informe del administrador empresarial es el primero de cuatro valiosos informes que su diseño en todos los detalles de documentos. La información en este informe, como en los otros tres informes asociados, es útil para los equipos de tecnologías de la información:

![Informe de administración de resúmenes generales](../../media/General_Summary_Report_Admin_Report.png)

En el informe de resumen se recoge la información de configuración general relativa a la red perimetral. Se documenta la ubicación, el nombre de dominio completo y la dirección IP, el tipo de red y los comentarios específicos de un rol en particular.

El diseñador y cada uno de los equipos encargados de implementar, administrar y mantener la infraestructura deben revisar el informe de resumen en busca de datos precisos para asegurarse de que los errores se reduzcan al mínimo.

También puede ver informes más detallados:

- Informe de certificados

- Informe de firewall

- Informe de DNS

## <a name="review-the-certificates-report"></a>Revisión del informe de certificados
<a name="Certificates_Report"> </a>

El informe de certificados contiene todos los certificados que se necesitan en el Skype recomendada para la implementación empresarial Server 2015. La herramienta de planeación de cuentas para los nombres de sujeto y nombre alternativo de sujeto que se hayan especificado. El texto predeterminado que se deja sin editar puede representar un posible desafío para el equipo responsable de solicitar y emitir los certificados. La información del certificado también contiene datos sobre el origen desde el cual puede emitirse normalmente el certificado. Si la infraestructura no dispone de una infraestructura de clave pública (PKI) interna, todos los certificados se pueden solicitar a través de un proveedor de certificados público. Los campos “Uso mejorado de clave (EKU)” y “Asignar a” del informe son muy útiles para comprender el objetivo y la ubicación de cada certificado.

![Informe de administración de certificados](../../media/Certificates_Report_Admin_Report.png)

Revise con atención y comprenda completamente el uso y el propósito de cada certificado de la implementación. Si tiene alguna pregunta acerca de la función de un certificado, determine los elementos con los que se comunica un servidor o servicio. Se usan los certificados en Skype para Business Server 2015 para dos principales objetivos:

- Seguridad de la capa de transporte mutua (MTLS) - los equipos necesarios para la comunicación presentan un certificado que demuestre su identidad a otro equipo. Esto se conoce como autenticación de servidor. No se puede iniciar la comunicación hasta que la identidad del otro equipo confía en cada equipo.

- Cifrado - cifrado (capa de Sockets seguros, o SSL y seguridad de la capa de transporte o TLS) es un método crítico para ayudar a comunicaciones seguras, ayudar a garantizar la privacidad y para crear un sistema de comunicaciones y colaboración de confianza.

## <a name="review-the-firewall-report"></a>Revisar el informe de firewall
<a name="Firewall_report"> </a>

Skype para Business Server 2015 tiene un conjunto de reglas de firewall potencialmente complejo. La herramienta de planeación reduce esta complejidad al generar un informe que define con detalle todos los requisitos de firewall, en función de criterios de entrada del diseñador. El administrador de firewall de TI podrá usar este informe para configurar y definir las reglas necesarias.

Desde el punto de vista de la administración del firewall, el informe deberá revisarse atentamente para garantizar que no haya conflictos con reglas de firewall existentes y que no haya directivas ni procedimientos infringidos.

![Informe de administración de firewall](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Revisar el informe de DNS
<a name="DNS_Report"> </a>

El informe de DNS, que forma parte de los informes de administrador, detalla todas las entradas recomendadas y conocidas del sistema de nombres de dominio (DNS) para las redes interna, perimetral y externa. Si el diseñador ha completado las ediciones del diagrama de red y ha establecido todas las direcciones IP y los nombres de dominio completos (FQDN) en sus valores de producción, el informe de DNS representa un recurso de configuración excelente. Asimismo, se trata de un documento de solución de problemas operativos.

![Informe de administración de DNS](../../media/DNS_Report_Admin_Report.png)

Deberá hacer que el equipo de administración de DNS revise completamente el informe de DNS para asegurarse de que no haya errores que puedan provocar alguna dificultad durante la implementación o que compliquen una sesión de solución de problemas.

## <a name="see-also"></a>Vea también
<a name="DNS_Report"> </a>

[Reviewing the Administrator Reports](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
