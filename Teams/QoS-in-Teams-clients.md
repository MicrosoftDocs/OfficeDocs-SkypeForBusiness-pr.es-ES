---
title: Implementar la calidad de servicio en los clientes de Teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Implemente la calidad de servicio (QoS) para los clientes de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 66e6dc43e03f1ec3606116ad001f11104de4a55f
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139609"
---
# <a name="set-qos-on-windows-clients"></a>Configurar QoS en clientes de Windows

Puede usar QoS basada en directivas en la Directiva de grupo para establecer el intervalo de puertos de origen para el valor predefinido de DSCP en el cliente de Teams. Los intervalos de puertos especificados en la tabla siguiente son un punto de partida para crear una directiva para cada carga de trabajo.

*Tabla 1. Intervalos de puerto iniciales recomendados*

|Tipo de tráfico de medios | Rango de puertos de origen del cliente  |Protocolo|Valor de DSCP|Clase DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50 000 – 50 019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50 020 – 50 039|TCP/UDP|34|Desvío garantizado (AF41)|
|Aplicación/Compartir pantalla| 50 040 – 50 059|TCP/UDP|18|Desvío garantizado (AF21)|
| | | | | |

Siempre que sea posible, establezca la configuración de QoS basada en directivas dentro de un objeto de directiva de grupo. Los pasos siguientes son muy similares a la [configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes de Skype empresarial Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tiene algunos detalles adicionales que pueden no ser necesarios.

Para crear una directiva de audio de QoS para equipos con Windows 10 Unidos a un dominio, primero debe iniciar sesión en un equipo en el que se haya instalado administración de directivas de grupo. Abra administración de directivas de grupo (haga clic en Inicio, seleccione Herramientas administrativas y, a continuación, haga clic en administración de directivas de grupo) y siga los pasos siguientes:

1. En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva. Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada **clientes**, la nueva Directiva debe crearse en la unidad organizativa clientes.

1. Haga clic con el botón secundario en el contenedor correspondiente y, después, haga clic en **crear un GPO en este dominio y vincúlelo aquí**.

1. En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.

1. Haga clic con el botón secundario en la Directiva recién creada y luego haga clic en **Editar**.

1. En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.

1. En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva en el cuadro **nombre** . Seleccione **especificar valor de DSCP** y establezca el valor en **46**. Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.

1. En la página siguiente, seleccione **solo las aplicaciones con este nombre de archivo ejecutable** **y, a**continuación, haga clic en **siguiente**. Esta configuración indica a la Directiva que solo asigne prioridad al tráfico coincidente del cliente de equipos.

1. En la tercera página, asegúrese de que **todas las direcciones IP de origen** y **cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**. Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado los paquetes y del equipo (dirección IP) que recibirá los paquetes.

1. En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo al que se aplica esta directiva de QoS** . TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados.

1. En el encabezado, **especifique el número de puerto de origen**, seleccione **de este rango o puerto de origen**. En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio. Por ejemplo, si ha reservado los puertos 50000 a través de los puertos 50019 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50000:50019**. Haga clic en **Finalizar**.

1. Repita los pasos 5-10 para crear directivas de vídeo y de uso compartido de aplicaciones y escritorio, sustituyendo los valores correspondientes en los pasos 6 y 10.

Las nuevas directivas que haya creado no surtirán efecto hasta que se actualice la Directiva de grupo en los equipos cliente. Aunque la Directiva de grupo se actualiza periódicamente por su cuenta, puede forzar una actualización inmediata siguiendo estos pasos:

1. En cada equipo para el que desee actualizar la Directiva de grupo, abra un símbolo del sistema como administrador (*Ejecutar como administrador*).

1. En el símbolo del sistema, escriba

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Comprobar las marcas de DSCP en el objeto de directiva de grupo

Para comprobar que se han establecido los valores del objeto de directiva de grupo, siga estos pasos:

1. Abra un símbolo del sistema como administrador (*Ejecutar como administrador*).

1. En el símbolo del sistema, escriba

   ```console
   gpresult /R > gp.txt
   ```

   Esto generará un informe de los GPO aplicados y lo enviará a un archivo de texto denominado *GP. txt*.

   Para obtener un informe HTML más legible denominado *GP. html*, escriba el siguiente comando:

   ```console
   gpresult /H gp.html
   ```

1. En el archivo generado, busque el encabezado **Applied Group Policy Objects** y compruebe que los nombres de los objetos de directiva de grupo creados anteriormente se encuentran en la lista de directivas aplicadas.

1. Abra el editor del registro y vaya a

   Directivas\_\\de\_software\\\\del equipo local\\de\\HKEY Microsoft Windows QoS

   Compruebe los valores de las entradas del registro que se muestran en la tabla 2.

   *Tabla 2. Valores de las entradas del registro de Windows para QoS*

   |          Nombre          |  Tipo  |    Datos     |
   |         :---:          | :---:  |    :---:    |
   |    Nombre de la aplicación    | REG_SZ |  Teams.exe  |
   |       Valor de DSCP       | REG_SZ |     46      |
   |        IP local        | REG_SZ |     \*      |
   | Longitud del prefijo de IP local | REG_SZ |     \*      |
   |       Puerto local       | REG_SZ | 50000-50019 |
   |        Protocolo        | REG_SZ |     \*      |
   |       IP remota        | REG_SZ |     \*      |
   |    Prefijo IP remoto    | REG_SZ |     \*      |
   |      Puerto remoto       | REG_SZ |     \*      |
   |     Velocidad de limitación      | REG_SZ |     -1      |
   | | | |

1. Compruebe que el valor de la entrada del nombre de la aplicación es correcto para el cliente que está usando y compruebe que tanto el valor de DSCP como las entradas del puerto local reflejan la configuración del objeto de directiva de grupo.
