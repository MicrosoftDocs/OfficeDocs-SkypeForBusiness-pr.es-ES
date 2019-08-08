---
title: Implementar Calidad de servicio en clientes de Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Implemente la calidad de servicio (QoS) para los clientes de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91b761cafa15172ae3fb0126f5059408e1a5f7ca
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36246201"
---
# <a name="set-qos-on-windows-clients"></a>Configurar QoS en clientes de Windows

Puede usar QoS basada en directivas en la Directiva de grupo para establecer el intervalo de puertos de origen para el valor predefinido de DSCP en el cliente de Teams. Los intervalos de puertos especificados en la tabla siguiente son un punto de partida para crear una directiva para cada carga de trabajo.

_Intervalos de puerto iniciales recomendados_

Tipo de tráfico multimedia| Intervalo de puertos de origen del cliente |Protocolo|Valor de DSCP|Clase de DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50000 – 50019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50,020–50,039|TCP/UDP|34|Desvío garantizado (AF41)|
|Aplicación/pantalla compartida| 50,040–50,059|TCP/UDP|18|Reenvío asegurado (AF21)|
| | | | |

Siempre que sea posible, establezca la configuración de QoS basada en directivas dentro de un objeto de directiva de grupo. Los pasos siguientes son muy similares a la [configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes de Skype empresarial Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tiene algunos detalles adicionales que pueden no ser necesarios.

Para crear una directiva de audio de QoS para equipos con Windows 10 Unidos a un dominio, primero debe iniciar sesión en un equipo en el que se haya instalado administración de directivas de grupo. Abra administración de directivas de grupo (haga clic en Inicio, seleccione Herramientas administrativas y, a continuación, haga clic en administración de directivas de grupo) y siga los pasos siguientes:

1. En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva. Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada **clientes**, la nueva Directiva debe crearse en la uo cliente.

2. Haga clic con el botón secundario en el contenedor correspondiente y, después, haga clic en **crear un GPO en este dominio y vincúlelo aquí**.

3. En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.

4. Haga clic con el botón secundario en la Directiva recién creada y luego haga clic en **Editar**.

5. En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.

6. En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva en el cuadro **nombre** . Seleccione **especificar valor de DSCP** y establezca el valor en **46**. Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.

7. En la página siguiente, seleccione **solo las aplicaciones con este nombre de archivo ejecutable** y, **** a continuación, haga clic en **siguiente**. Esta configuración indica a la Directiva que solo asigne prioridad al tráfico coincidente del cliente de equipos.

8. En la tercera página, asegúrese de que **todas las direcciones IP de origen** y **cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**. Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado los paquetes y del equipo (dirección IP) que recibirá los paquetes.

9. En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo al que se aplica esta directiva de QoS** . TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados.

10. En el encabezado, **especifique el número de puerto de origen**, seleccione **de este rango o puerto de origen**. En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio. Por ejemplo, si ha reservado los puertos 50000 a través de los puertos 50019 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50000:50019**. Haga clic en **Finalizar**.

11. Repita los pasos 5-10 para crear directivas de vídeo y de uso compartido de aplicaciones y escritorio, sustituyendo los valores correspondientes en los pasos 6 y 10.

Las nuevas directivas que haya creado no surtirán efecto hasta que se actualice la Directiva de grupo en los equipos cliente. Aunque la Directiva de grupo se actualiza periódicamente por su cuenta, puede forzar una actualización inmediata siguiendo estos pasos:

1. En cada equipo para el que desee actualizar la Directiva de grupo, abra una consola de comandos. Asegúrese de que la consola de comandos está configurada para ejecutarse como administrador.

2. En el símbolo del sistema, escriba

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Comprobar las marcas de DSCP en el objeto de directiva de grupo

Para comprobar que se han establecido los valores del objeto de directiva de grupo, siga estos pasos.

1. Abra una consola de comandos. Asegúrese de que la consola de comandos está configurada para ejecutarse como administrador.

2. En el símbolo del sistema, escriba:

   ``` powershell
   gpresult /R > gp.txt
   ```

   Esto generará un informe y lo enviará a un archivo de texto denominado GP. txt. Como alternativa, puede escribir el siguiente comando para generar los mismos datos en un informe HTML más legible denominado GP. html:

   ``` powershell
   gpresult /H >gp.html
   ```

   ![Captura de pantalla de la ventana de la consola que ejecuta el comando Gpresult.] (media/Qos-in-Teams-Image3.png "Captura de pantalla de la ventana de la consola que ejecuta el comando Gpresult.")

3. En el archivo generado, busque el encabezado **Applied Group Policy Objects** y compruebe que los nombres de los objetos de directiva de grupo creados anteriormente se encuentran en la lista de directivas aplicadas.

4. Abra el editor del registro y vaya a:

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Compruebe los valores de las entradas del registro que se muestran en la tabla 4.

   _Tabla 4. Valores de las entradas del registro de Windows para QoS_

   |          Nombre          |  Tipo  |    Datos     |
   |         :---:          |:---:   |    :---:    |
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

5. Compruebe que el valor de la entrada del nombre de la aplicación es correcto para el cliente que está usando y compruebe que tanto el valor de DSCP como las entradas del puerto local reflejan la configuración del objeto de directiva de grupo.
