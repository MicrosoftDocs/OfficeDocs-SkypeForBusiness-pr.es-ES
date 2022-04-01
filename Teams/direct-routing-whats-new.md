---
title: Novedades del enrutamiento directo
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: En este artículo se describen las novedades de Enrutamiento directo. Vuelva a buscar actualizaciones a menudo.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53a1c2730ebf6db06fb92ac2fc4e0873563c98ce
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584335"
---
# <a name="whats-new-for-direct-routing"></a>Novedades de Enrutamiento directo

En este artículo se describen las novedades de Enrutamiento directo. Vuelva a buscar actualizaciones a menudo.

## <a name="sip-support"></a>Compatibilidad con SIP

El 1 de junio de 2022, Microsoft quitará la compatibilidad con sip-all.pstnhub.microsoft.com y sip-all.pstnhub.gov.teams.microsoft.us FQDN de la configuración de enrutamiento directo.

Si no se realiza ninguna acción antes del 1 de junio, los usuarios no podrán realizar ni recibir llamadas a través del enrutamiento directo.

Para evitar el impacto en el servicio:

- Use las subredes recomendadas: (52.112.0.0/14 y 52.120.0.0/14) para cualquier regla de clasificación o ACL.
- Deje de usar el FQDN sip-all al configurar controles de borde de sesión para enrutamiento directo.

Para obtener más información, vea [Planear enrutamiento directo](direct-routing-plan.md).

## <a name="tls-certificates"></a>Certificados TLS

Microsoft 365 está actualizando Teams y otros servicios para usar un conjunto diferente de autoridades de certificación raíz (CA).

Para obtener más información y una lista completa de los servicios afectados, vea Cambios en el certificado [TLS en Microsoft 365 servicios incluidos Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676).

## <a name="certificate-authorities"></a>Autoridades de certificación

A partir del 1 de febrero de 2022, la interfaz SIP de enrutamiento directo solo confiará en los certificados firmados por las entidades de certificación (CA) que forman parte del Programa de certificados raíz de confianza de Microsoft. Siga estos pasos para evitar el impacto en el servicio:

- Asegúrese de que su certificado SBC está firmado por una entidad de certificación que forma parte del Programa de certificados raíz de confianza de Microsoft.
- Compruebe que la extensión Uso de clave extendida (EKU) del certificado incluye "Autenticación de servidor".

Para obtener más información sobre el Programa de certificados raíz de confianza de Microsoft, vea [Requisitos del programa : Programa raíz de confianza de Microsoft](/security/trusted-root/program-requirements).

Para obtener una lista de ca de confianza, vea [Lista de certificados de CA incluidas de Microsoft](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Reemplazar encabezados

A partir de abril de 2022, enrutamiento directo rechazará las solicitudes SIP que tengan definidos los encabezados Reemplazar. No hay cambios en los flujos en los que Microsoft envía el encabezado Reemplazars al controlador de borde de sesión(SBC).

Compruebe las configuraciones de SBC y asegúrese de que no está usando Reemplazar encabezados en solicitudes SIP.

## <a name="tls10-and-11"></a>TLS1.0 y 1.1

Para proporcionar el mejor cifrado de su clase a nuestros clientes, Microsoft planea desuso de las versiones 1.0 y 1.1 de seguridad de la capa de transporte (TLS). El 3 de abril de 2022, Microsoft forzará el uso de TLS1.2 para la interfaz SIP de enrutamiento directo.

Para evitar cualquier impacto en el servicio, asegúrese de que los SBC están configurados para admitir TLS1.2 y puede conectarse con uno de los siguientes conjuntos de cifrado:

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 es decir, ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 es decir, ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 es decir, ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 es decir, ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Temas relacionados

- [Enrutamiento directo: protocolo SIP](direct-routing-protocols-sip.md)
