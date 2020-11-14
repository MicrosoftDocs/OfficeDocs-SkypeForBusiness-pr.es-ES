---
title: Usar el Asistente para introducción para configurar Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
- m365initiative-voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53636ada916fec05bf75ef8947cdab44e38644e2
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030616"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>Usar el Asistente para introducción para configurar Business Voice

> [!IMPORTANT]
> La información contenida en este artículo se aplica al plan de llamadas **de** Business Voice. El plan de llamadas de Business Voice está disponible solo en determinados países y regiones. Antes de leer este artículo, compruebe la [disponibilidad de países y regiones de Business Voice](country-region-availability.md) para ver si su país o región admite el plan de llamadas de Business Voice.
>
> Si su espacio empresarial se encuentra en un país o región que no admita el plan de llamadas de Business Voice, consulte [Obtener ayuda de un revendedor o partner de Microsoft](reseller-partner-support.md).

El Asistente de introducción a Microsoft 365 Business Voice le ayuda a configurarla rápidamente para realizar y recibir llamadas de teléfono en Microsoft Teams. Si usted es una pequeña empresa que acaba de empezar, el asistente permite ponerse en marcha en unos minutos con números de teléfono, menús de llamadas, saludos y mucho más. Si es un empresa grande con una solución de telefonía establecida, el asistente puede ayudarle a configurar una prueba piloto de Business Voice para que unos pocos usuarios puedan probarlo antes de configurarlo para todos. En cualquier caso, puede empezar a usar Business Voice tan pronto como finalice el asistente.

Es una buena idea leer este artículo antes de iniciar el asistente. Cuando este listo para ejecutar el asistente, seleccione **Comenzar** en la página [Comenzar con Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice). Inicie sesión con la cuenta que usó para crear la suscripción o con otra cuenta que sea un administrador global.

> [!IMPORTANT]
> Microsoft Teams y Business Voice solo funcionan cuando los buzones de los usuarios se encuentran ubicados en Microsoft 365.  No admiten buzones de correo en servidores de Exchange locales.
>
> El Asistente para introducción no es compatible con las implementaciones híbridas de Skype Empresarial. Si tiene una implementación híbrida de Skype Empresarial y quiere configurar Business Voice, consulte [Configurar el sistema telefónico en la organización](../setting-up-your-phone-system.md).

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

Si no quiere personalizar nada por ahora, ya ha terminado. Puede empezar a usar Business Voice inmediatamente.

## <a name="emergency-services-location"></a>Ubicación de servicios de emergencia

<table>
    <tr>
        <td>Si quiere cambiar la dirección de emergencia, haga clic en <b>Editar</b> y escriba una dirección nueva. La dirección que proporcione se validará para asegurar que es legítima y tiene el formato correcto para los servicios de respuesta de emergencia. Después, esta dirección se asigna a todos los usuarios a los que asigne un número en el siguiente paso. Si tiene empleados en más de una ubicación, consulte <a href="./customize-business-voice.md">Personalización de diseño de Business Voice</a> para agregar y asignar más direcciones de emergencia después de preparar el Asistente de introducción.</td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400"></td></tr>
</table>

Si quiere más información, vea [¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](../what-are-emergency-locations-addresses-and-call-routing.md)

## <a name="company-phone-number"></a>Número de teléfono de la empresa

<table>
    <tr>
        <td>Además de un nuevo número de teléfono local, puede comprar un número gratuito o trasladar un número existente a Microsoft 365. Para configurar un número gratuito, tendrá que comprar Créditos de comunicaciones. Para migrar uno o más números a Microsoft 365, vaya al <a href="https://admin.teams.microsoft.com">Centro de administración de Teams</a> cuando finalice el asistente.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Si traslada un número de teléfono existente a Microsoft 365, aún verá un número de teléfono temporal en el asistente. Esto es normal. Cuando finalice el asistente y el proceso de traslado, el número de teléfono temporal se reemplazará por el número ya existente.

## <a name="user-licenses"></a>Licencias de usuario

<table>
    <tr>
        <td>Para asignar licencias de usuario, seleccione las personas de su organización que necesiten realizar o recibir llamadas de teléfono fuera de Teams (como llamar a un proveedor). Solo puede asignar las licencias de Business Voices que tenga disponibles. Si necesita más, puede comprar licencias adicionales cuando finalice el asistente.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Puede trasladar números de teléfono existentes a Microsoft 365 después de que finalice el asistente. Cuando termine el proceso de traslado, los números de teléfono trasladados reemplazarán los números de teléfono temporales seleccionados por el asistente.

## <a name="incoming-call-greeting"></a>Saludos de llamada entrante

<table>
    <tr>
        <td>Puede cargar un archivo de sonido (MP3 o WAV) de hasta 5 megabytes (MB) para usarlo como saludo o puede escribir el saludo y Microsoft 365 usará la función de texto a voz para leerlo al autor de la llamada. El saludo es lo primero que los autores de llamadas escuchan cuando llaman al número de teléfono de la empresa. Para la opción de texto a voz, es posible que tenga que escribir las palabras fonéticamente para que las pronunciaciones sean correctas.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>Menú de llamada y reenvío

<table>
    <tr>
        <td>Se pueden reenviar todas las llamadas a un usuario específico o se puede configurar un menú de llamadas en el que el autor de la llamada puede elegir opciones. Si crea un menú de llamadas, especificará las opciones que el autor de la llamada puede seleccionar por voz o presionando un número en el teclado del teléfono. Cada opción del menú puede reenviar llamadas a un usuario específico.<br><br>
        Puede cargar un archivo de sonido (MP3 o WAV) de hasta 5 MB que proporcione instrucciones al autor de llamada, o bien puede escribir las instrucciones. Microsoft 365 usará la función de texto a voz para leer las instrucciones al autor de la llamada. Es posible que sea necesario deletrear las palabras para que las pronunciaciones sean correctas.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> El Asistente de introducción le ayuda a configurar un menú de llamadas simple para que pueda empezar a trabajar rápidamente. Si tiene varios números de teléfono en los que quiere configurar menús de llamadas, o si quiere configurar menús de llamadas más complejos (también llamados operadores automáticos), consulte [Configurar un operador automático en la nube](set-up-auto-attendants.md) después de finalizar el asistente.

<table>
    <tr>
        <td> <p>El Asistente de introducción toma la información que especifique y configura Business Voice. En la página de <b>Información general</b>, puede ver los números de teléfono que se asignarán a los usuarios, echar un vistazo al menú de llamadas, escuchar el saludo y mucho más.</p>
             <p>La instalación tarda varios minutos. Si selecciona <b>Listo</b>, seguiremos configurando Business Voice en segundo plano. O bien, puede esperar hasta que finalice la instalación. Cuando termine, vaya a <b>Voz</b> en el <a href="https://admin.teams.microsoft.com" target="_blank">Centro de administración de Teams</a> para configurar más características de Business Voice.</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>
