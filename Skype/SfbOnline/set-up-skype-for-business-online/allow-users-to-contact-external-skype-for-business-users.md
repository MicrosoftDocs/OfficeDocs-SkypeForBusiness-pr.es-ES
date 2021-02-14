---
title: Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'Vea cómo configurar Skype Empresarial para permitir que los usuarios hablen con los usuarios de otra organización o que los contactos externos hablen con ellos. '
ms.openlocfilehash: d9b3be381432fa95962df7a5a58ea9d81e223fc4
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625056"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial
  
Siga los pasos de este artículo cuando:
  
- Haya usuarios de diferentes dominios en su empresa. Por ejemplo, Rob@ContosoEste.com y Ann@ContosoOeste.com.

- Desee que las personas de su empresa puedan usar Skype Empresarial para ponerse en contacto con personas de empresas específicas de fuera de su organización.

- Desea que cualquier otra persona del mundo que use Skype Empresarial pueda buscarlo y ponerse en contacto con usted mediante su dirección de correo electrónico. Si usted y ellos usan la configuración predeterminada de Skype Empresarial, esto funcionará automáticamente. Si no es así, deben asegurarse de que la configuración no está bloqueando el dominio.

## <a name="enable-business-to-business-communications-for-your-users"></a>Habilitar comunicaciones entre empresas para los usuarios

<a name="bk_preview"> </a>

Debe tener permisos [de administrador en](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Microsoft 365 u Office 365 en ambas organizaciones para realizar esta comunicación.

![Icono que muestra el logotipo de Microsoft Teams ](../images/teams-logo-30x30.png) **Con el Centro de administración de Teams**
  
1. Inicie sesión con su cuenta de administrador de Microsoft 365 u Office 365.

2. En el centro de administración, vaya a **Equipos de centros de**  >  **administración.**

    ![Elija el administrador de Teams.](../images/MS-Teams-Admin.png)
  
3. En el **Centro de equipos,** elija **Skype** > **(portal** 
  ![ heredado) Elija el portal heredado de SfB.](../images/SFBlegacy-size65.png)

4. En el **Centro de administración de Skype Empresarial**, seleccione **Organización** > **Comunicaciones externas**.
5. Para configurar la comunicación con empresas específicas o con usuarios de otros dominios, seleccione en el cuadro desplegable **Activado solo para dominios permitidos**.

    O BIEN, si desea habilitar la comunicación con todo el mundo que tenga directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta es la configuración predeterminada.

6. En **Dominios bloqueados o permitidos,** elija y agregue el nombre del **+** dominio que desea permitir.

7. Asegúrese de que el administrador de la otra organización realiza estos mismos pasos en su **Centro de administración de Skype Empresarial.** Por ejemplo, en su lista de **dominios permitidos**, el otro administrador tendrá que especificar el dominio de la empresa de la que usted forma parte.

8. Si usa el Firewall de Windows, Skype Empresarial abre automáticamente los puertos solicitados.

    Si su organización usa una solución de firewall diferente para restringir la conexión a Internet de los equipos en la red, asegúrese de que sus equipos cliente pueden acceder a los siguientes [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges). Esto puede requerir agregar los FQDN a la lista de permitidos de salida en la configuración de infraestructura de proxy o firewall: **\* .api.skype.com,** \* **.users.storage.live.com** **y graph.skype.com.** Para obtener instrucciones sobre cómo abrir estos puertos en el firewall, consulta la documentación proporcionada.

    Para obtener una lista de todos los puertos que debe abrir, vea las URL de [Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)y los intervalos de direcciones IP.

9. Asegúrese de que el administrador de la organización también ha seguido estos pasos.

10. **AGUARDE HASTA 24 HORAS PARA LA PRUEBA**. Cuando cambia la configuración de comunicaciones externas, los cambios pueden tardar hasta 24 horas en completarse en todos los centros de datos.

![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Puede permitir a los usuarios que busquen a todos los que usen Skype, la aplicación de consumidor gratuita, y que se comuniquen con ellos con mensajería instantánea. Para obtener más información, vea Permitir que los [usuarios de Skype Empresarial agreguen contactos de Skype.](let-skype-for-business-users-add-skype-contacts.md)
  
## <a name="test-and-troubleshoot"></a>Probar y solucionar problemas

<a name="bk_preview"> </a>

 **El problema más común que se encuentran los usuarios al configurar la comunicación entre empresas es [URL de Office 365 e intervalos de direcciones IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) correctamente.**
  
Para probar su instalación, necesita un contacto en Skype Empresarial que no esté bloqueado por el firewall de su empresa.
  
1. Una vez que cambie la configuración de las comunicaciones externas, **DEBE ESPERAR 24 HORAS PARA PODER REALIZAR LAS PRUEBAS**.

2. En Skype Empresarial, busque su contacto en Skype Empresarial y envíe una solicitud para chatear.

    Si recibe un mensaje que indica que no se pudo enviar debido a la directiva de la empresa, tendrá que volver a comprobar sus direcciones URL e intervalos de direcciones IP de [Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)

3. Pida a su contacto de Skype Empresarial que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).

4. Otra forma de comprobar si el problema es del firewall es ir a un lugar que no esté bloqueado por el firewall, como una cafetería. Use Skype Empresarial para enviar una solicitud a su contacto para chatear. Si el mensaje se envía en ese momento, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Cómo buscar a otros, y permitir que me encuentren, al conectarme con otro negocio

<a name="bk_preview"> </a>

Después de habilitar la comunicación externa con otros usuarios de Skype Empresarial, los usuarios pueden buscar usuarios federados de Skype Empresarial buscando sus nombres de inicio de sesión. Un ejemplo es Rob@contoso.com. Luego deben agregar a la persona a su lista de contactos.
  
![Para buscar un usuario en una empresa federada, debe buscar su dirección de correo electrónico (normalmente también es su nombre de inicio de sesión).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Sugerencias para configurar las comunicaciones con empresas federadas

<a name="bk_preview"> </a>

- Para configurar la federación entre Skype Empresarial 2015 y Skype Empresarial Online, consulte este artículo: Configurar la federación [con Skype Empresarial Online.](https://technet.microsoft.com/library/jj205126.aspx)

- Para configurar la federación entre Lync y Skype Empresarial Online, consulte este artículo: Configurar la compatibilidad de federación [para un cliente de Lync Online.](https://technet.microsoft.com/library/hh202193.aspx)

- Cuando dos usuarios de Skype Empresarial en Microsoft 365 u Office 365 se comunican entre sí en dominios independientes, solo pueden usar las características de Skype Empresarial (por ejemplo, conversaciones de vídeo o uso compartido del escritorio) que están activadas en ambas organizaciones.

- Si un usuario de Skype Empresarial de su organización se pone en retención por juicio o In-Place, todas las  conversaciones de mensajería instantánea entre ese usuario y otros usuarios de Skype Empresarial o Skype se guardarán en Elementos recuperables de su buzón. Estas conversaciones no se guardarán en la carpeta **Historial de conversaciones** de su buzón.

## <a name="turn-off-external-communication-for-specific-individuals"></a>Desactivar la comunicación externa para personas específicas

<a name="bk_preview"> </a>

Después de habilitar la comunicación externa para toda su empresa, puede desactivarla para personas específicas solamente.
  
1. Inicie sesión con su cuenta de administrador de Microsoft 365 u Office 365.

2. En el centro de administración, vaya a **Usuarios**  >  **activos.**

3. En la lista de usuarios, elija el usuario y, a continuación, en **Más configuraciones**, haga clic en **Editar propiedades de Skype Empresarial**.

    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. En el **Centro de administración de Skype Empresarial,** elija **Comunicaciones externas.**

    En la **página** Opciones, se seleccionarán todas las opciones. Desactive las comunicaciones que desee deshabilitar. En la siguiente imagen se muestra que Jakob podrá comunicarse con personas de otras empresas de confianza, pero no con otros usuarios de Skype.

    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Elija **Guardar**.

> [!NOTE]
> Es posible que haya que esperar hasta 24 horas para que los cambios tengan efecto.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Temas relacionados

<a name="bk_preview"> </a>

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)
  