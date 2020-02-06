---
title: Pruebas de recuperación ante desastres en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Realizar una recuperación del sistema de un servidor del grupo de servidores de Skype empresarial para probar el proceso de recuperación ante desastres documentado
ms.openlocfilehash: f3eba25d59c56f085b9bd6d347fcde910f11a00d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817306"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Pruebas de recuperación ante desastres en Skype empresarial Server

Realice una recuperación del sistema de un servidor del grupo de servidores de Skype empresarial para probar el proceso de recuperación ante desastres documentado. Esta prueba simulará un error de hardware completo para un servidor y le ayudará a garantizar que los recursos, los planes y los datos estén disponibles para la recuperación. Trate de variar cada mes el objeto de esta simulación, de modo que su organización vaya poniendo a prueba distintos servidores u otros elementos. 

Tenga en cuenta que el programa mediante el cual las organizaciones realizan pruebas de recuperación ante desastres puede variar. Es muy importante no ignorar o descuidar estas pruebas. 

Exporte la topología, las directivas y los parámetros de configuración de Skype empresarial Server a un archivo. Entre otras cosas, este archivo podrá usarse para restaurar esta información en el Almacén de administración central después de una actualización, un error de hardware o cualquier otro problema que resulte en la pérdida de datos.

Importe la topología, las directivas y las opciones de configuración de Skype empresarial Server en el almacén de administración central o en el equipo local, tal y como se muestra en los siguientes comandos: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Para hacer una copia de seguridad de los datos de producción:

- Haga una copia de seguridad de las bases de datos RTC y LCSLog con el proceso de copia de seguridad estándar de SQL Server para volcar la base de datos en un dispositivo de volcado de archivo o cinta.
- Use una aplicación de terceros para realizar en un archivo o cinta una copia de seguridad de los datos.
- Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.
- Use la copia de seguridad del sistema de archivos o la copia de seguridad de terceros para realizar copias de seguridad de contenido y registros de cumplimiento.
- Use la herramienta de línea de comandos Export-CsConfiguration para realizar copias de seguridad de la configuración de Skype empresarial Server.

El primer paso en el procedimiento de conmutación por error incluye el traslado forzoso de los usuarios desde el grupo de producción al grupo de recuperación ante desastres. Se trata de un traslado forzoso porque el grupo de producción no estará disponible para aceptar la reubicación de los usuarios.

El proceso para mover usuarios de Skype empresarial Server es en realidad un cambio en un atributo en el objeto de cuenta de usuario, además de una actualización de registro en la base de datos de SQL de RTC. Estos datos se pueden restaurar desde el dispositivo de volcado de la copia de seguridad original desde el servidor SQL de producción mediante el proceso de restauración estándar de SQL Server o mediante una herramienta de copia de seguridad y restauración de terceros.

Una vez que se hayan restaurado estos datos, los usuarios podrán conectarse al grupo de recuperación de desastres y funcionar de la forma habitual. Para permitir que los usuarios se conecten al grupo de recuperación de desastres, será necesario un cambio de registro DNS.

Los clientes hará referencia al grupo de producción de Skype empresarial mediante la configuración automática y los registros SRV de DNS de:

- SRV: _sip. _tls. \<Domain>/CNAME: SIP. \<> de dominio
- CNAME: SIP. \<> de dominio de/CVC-Pool-1. \<> de dominio

Para facilitar la conmutación por error, este registro CNAME debe actualizarse para que haga referencia al FQDN DROCSPool:

- CNAME: SIP.<domain> /DROCSPool. \<> de dominio
- SIP. \<> de dominio
- > del\<dominio AV
- WebConf. \<> de dominio
