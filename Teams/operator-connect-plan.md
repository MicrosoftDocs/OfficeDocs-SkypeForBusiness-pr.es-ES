---
title: Operador Conectar
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre las Conectar operadores, como los requisitos y la planificación de la implementación.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694545"
---
# <a name="plan-for-operator-connect"></a>Plan para operadores Conectar

>[!NOTE]
>El Conectar operador solo está disponible actualmente en **la vista previa pública.** La vista previa pública le permite probar las próximas características y proporcionar comentarios. Es posible que las características incluidas en la vista previa pública no se completen, que se someten a cambios y que no se admiten en Office 365 Administración Pública nube.

Operador Conectar es otra opción para proporcionar conectividad de red telefónica conmutada (RTC) con Teams y Sistema telefónico.  

En este artículo se describen las ventajas y los requisitos, y se enumeran los operadores que participan en el Programa de Conectar operador.  Si decide operador Conectar es la solución adecuada para su [organización,](operator-connect-configure.md)después de leer este artículo, vea Configurar operador Conectar .  

## <a name="benefits"></a>Ventajas

Con Operador Conectar, si el operador existente es un participante en el programa operador de Microsoft Conectar, pueden administrar el servicio para llevar llamadas RTC a Teams. El programa Conectar operador proporciona las siguientes ventajas:

- **Aproveche los contratos existentes o busque un nuevo operador.** Mantiene su operador y contratos preferidos, o elige uno nuevo de una selección de operadores participantes para satisfacer sus necesidades empresariales.

- **Infraestructura administrada por operadores.** El operador administra los servicios de llamadas RTC y los controladores de borde de sesión (SBC), lo que le permite ahorrar en la compra y administración de hardware.

- **Implementación más rápida y sencilla.** Puede conectarse rápidamente a su operador y asignar números de teléfono a los usuarios, todo desde el Centro de Teams administración.

- **Soporte y confiabilidad mejorados.** Los operadores proporcionan soporte técnico y contratos de nivel de servicio compartido para mejorar el servicio de soporte técnico, mientras que el emparejamiento directo con tecnología de Azure crea una conexión de red uno a uno para mejorar la confiabilidad.

## <a name="requirements"></a>Requirements

 La Conectar operador podría ser la solución adecuada para su organización si:

- Microsoft Calling Plan no está disponible en su ubicación geográfica.
- Su operador preferido es un participante en el programa de Conectar microsoft.
- Desea buscar un operador nuevo para habilitar las llamadas en Teams.

Para habilitar las asignaciones de números de teléfono con Conectar operador, asegúrese de que los usuarios:

- Teams Teléfono licencia. Para obtener más información, vea [¿Qué Sistema telefónico?](what-is-phone-system-in-office-365.md) y Asignar Teams de complementos a [los usuarios.](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- En el modo TeamsOnly. Para obtener más información, vea [Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="available-operators"></a>Operadores disponibles

Los siguientes operadores son participantes en el programa de Conectar Microsoft Operator:

| Operador | Funcionalidad | Cobertura de país |
| --- | --- | --- |
| `BT`  | Llamadas | Bélgica, Dinamarca, Finlandia, Francia, Alemania, Irlanda, Italia, Luxemburgo, Países Bajos, Noruega, Polonia, Sudáfrica, España, Suecia, Suiza, Reino Unido |
| `Intrado` | Llamadas | Bélgica, Canadá, Dinamarca, Francia, Alemania, Irlanda, Luxemburgo, Países Bajos, España, Suecia, Reino Unido, Estados Unidos  |
| `NTT`  | Llamadas | Austria, Bélgica, Brasil, Canadá, Chequia, Dinamarca, Finlandia, Francia, Alemania, Irlanda, Italia, Luxemburgo, México, Países Bajos, Noruega, Polonia, Portugal, Puerto Rico, Rumania, Sudáfrica, España, Suecia, Suiza, Reino Unido, Estados Unidos |
| `NuWave` | Llamadas | Austria, Bélgica, Canadá, Dinamarca, Francia, Alemania, Irlanda, Italia, Países Bajos, Portugal, España, Suecia, Suiza, Reino Unido, Estados Unidos   |
| `Orange Business Services` | Llamadas | Austria, Bélgica, Chequia, Dinamarca, Finlandia, Francia, Guayana Francesa, Alemania, Guadalupe, Irlanda, Italia, Luxemburgo, Martinica, Mayotte, Países Bajos, Noruega, Polonia, Portugal, Reunión, San Martín, España, Svalbard, Suecia, Suiza, Reino Unido  |
| `Pure IP` | Llamadas | Australia, Austria, Bélgica, Brasil, Bulgaria, Canadá, Chile, Colombia, Croacia, Chipre, Chequia, Dinamarca, Finlandia, Francia, Alemania, Grecia, Hong Kong S.A.R., Irlanda, Italia, Japón, Lituania, Luxemburgo, Malasia, México, Países Bajos, Nueva Zelanda, Noruega, Panamá, Polonia, Portugal, Puerto Rico, Rumania, Singapur, Eslovaquia, Eslovenia, Sudáfrica, España, Suecia, Suiza, Reino Unido, Estados Unidos  |
| `Rogers Business` | Llamadas | Canadá  |
| `TATA Communications` | Llamadas | Australia, Austria, Bélgica, Canadá, Chequia, Dinamarca, Francia, Alemania, Hong Kong S.A.R., Hungría, Irlanda, Italia, Malasia, México, Países Bajos, Nueva Zelanda, Polonia, Portugal, Rumania, Singapur, Corea del Sur, España, Suecia, Suiza, Tailandia, Reino Unido, Estados Unidos |
| `Telekom Deutschland` | Llamadas | Alemania  |
| `Telenor` | Llamadas | Dinamarca, Finlandia, Noruega, Suecia  |
| `Verizon` | Llamadas | Estados Unidos |
