---
title: Implementar servidores perimetrales en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Summary: Learn how to deploy Edge Servers into your Skype Empresarial Server environment.'
ms.openlocfilehash: 6d098a78fe0fbb005bc023790e59416601eeab8c3c4d8b1378a71bfcf3d59a02
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305952"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Implementar servidores perimetrales en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo implementar servidores perimetrales en el entorno Skype Empresarial Server cliente.
  
Las secciones siguientes contienen los pasos que deben seguirse después de revisar Skype Empresarial Server [Plan for Edge Server deployments in Skype Empresarial Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) documentation. Los pasos de implementación son los siguientes:
  
- Interfaces de red
    
- Instalación
    
- Certificados
    
- Inicio de los servidores perimetrales
    
## <a name="network-interfaces"></a>Interfaces de red

Como se indica en Planeación, configurará la interfaz de red con DNS en la red perimetral que hospeda los servidores perimetrales o sin DNS en la red perimetral.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configuración de interfaz con servidores DNS en la red perimetral

1. Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz interna y otro para la interfaz externa.
    
    > [!NOTE]
    > Las subredes internas y externas no deben ser enrutables entre sí. 
  
2. En la interfaz externa, configurará **una de** las siguientes opciones:
    
   a. Tres direcciones IP estáticas en la subred de red perimetral externa y apunten la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure la configuración dns del adaptador para que apunte a un par de servidores DNS perimetrales.
    
   b. Una dirección IP estática en la subred de red perimetral externa y apuntar la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure la configuración dns del adaptador para que apunte a un par de servidores DNS perimetrales. Esta configuración solo es aceptable si ha configurado previamente la topología para que tenga valores no estándar en las asignaciones de puertos, que se describe en el artículo Crear la topología perimetral [para Skype Empresarial Server](create-your-edge-topology.md) servidor.
    
3. En la interfaz interna, configure una DIRECCIÓN IP estática en la subred de red perimetral interna y no establezca una puerta de enlace predeterminada. Configure la configuración dns del adaptador para que apunte al menos a un servidor DNS, pero preferiblemente a un par de servidores DNS perimetrales.
    
4. Cree rutas estáticas persistentes en la interfaz interna a todas las redes internas donde residen clientes, Skype Empresarial Server y Exchange de mensajería unificada (MU).
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configuración de interfaz sin servidores DNS en la red perimetral

1. Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz interna y otro para la interfaz externa.
    
    > [!NOTE]
    > Las subredes internas y externas no deben ser enrutables entre sí. 
  
2. En la interfaz externa, configurará **una de** las siguientes opciones:
    
   a. Tres direcciones IP estáticas en la subred de red perimetral externa. También tendrá que configurar la puerta de enlace predeterminada en la interfaz externa, por ejemplo, definiendo el enrutador orientado a Internet o el firewall externo como la puerta de enlace predeterminada. Configure la configuración dns del adaptador para que apunte a un servidor DNS externo, idealmente un par de servidores DNS externos.
    
   b. Una dirección IP estática en la subred de red perimetral externa. También tendrá que configurar la puerta de enlace predeterminada en la interfaz externa, por ejemplo, definiendo el enrutador orientado a Internet o el firewall externo como la puerta de enlace predeterminada. Configure la configuración dns del adaptador para que apunte a un servidor DNS externo o, idealmente, un par de servidores DNS externos. Esta configuración solo es aceptable si ha configurado previamente la topología para que tenga valores no estándar en las asignaciones de puertos, que se describe en el artículo Crear la topología perimetral [para Skype Empresarial Server](create-your-edge-topology.md) servidor.
    
3. En la interfaz interna, configure una DIRECCIÓN IP estática en la subred de red perimetral interna y no establezca una puerta de enlace predeterminada. También deje la configuración DNS del adaptador vacía.
    
4. Cree rutas estáticas persistentes en la interfaz interna a todas las redes internas donde residen clientes, Skype Empresarial Server y Exchange de mensajería unificada (MU).
    
5. Edite el archivo HOST en cada servidor perimetral para que contenga un registro para el servidor de próximo salto o la IP virtual (VIP). Este registro será el director, el Standard Edition o el grupo de servidores front-end que configuró como la dirección del próximo salto del servidor perimetral en el Generador de topologías. Si usa el equilibrio de carga DNS, incluya una línea para cada miembro del grupo de servidores de próximo salto.
    
## <a name="installation"></a>Instalación

Para completar estos pasos correctamente, deberá haber seguido los pasos del artículo [Create your Edge topology for Skype Empresarial Server.](create-your-edge-topology.md)
  
1. Inicie sesión en el servidor que ha estado configurando para el rol servidor perimetral con una cuenta que está en el grupo del administrador local.
    
2. Necesitará el archivo de configuración de topología que copió al final de la documentación de topología del servidor perimetral en este equipo. Accede a los medios externos en los que colocaste ese archivo de configuración (como una unidad USB o un recurso compartido).
    
3. Inicie el **Asistente para implementación**.
    
4. Una vez que se abra el asistente, haga clic en **Instalar o actualizar Skype Empresarial Server Sistema**.
    
5. El asistente ejecutará comprobaciones para ver si ya hay algo instalado. Como es la primera vez que se ejecuta el asistente, querrá empezar en el **paso 1. Instalar el almacén de configuración local.**
    
6. Aparecerá **el cuadro de diálogo** Configurar réplica local del almacén de administración central. Debe hacer clic en **Importar desde un archivo (recomendado para servidores perimetrales).**
    
7. Desde aquí, vaya a la ubicación de la topología que exportó anteriormente, seleccione el archivo .zip, haga clic en **Abrir** y, a continuación, haga clic en **Siguiente**.
    
8. El Asistente para la implementación leerá el archivo de configuración y escribirá el archivo de configuración XML en el equipo local.
    
9. Cuando el proceso **Ejecución de comandos** se complete, haga clic en **Finalizar**.
    
10. En el Asistente para implementación, haga clic **en Paso 2. Configurar o quitar Skype Empresarial Server componentes**. A continuación, el asistente instalará los Skype Empresarial Server edge especificados en el archivo de configuración XML que se ha almacenado en el equipo local.
    
11. Una vez completada la instalación, puede pasar a los pasos de la **sección Certificados que se muestran a** continuación.
    
## <a name="certificates"></a>Certificados

Los requisitos de certificado para el servidor perimetral se pueden encontrar en la documentación de planeación de certificados perimetrales. A continuación se indican los pasos para configurar certificados.
  
> [!NOTE]
> Al ejecutar el Asistente para certificados, debe iniciar sesión como una cuenta con los permisos correctos para el tipo de plantilla de certificado que va a usar. De forma predeterminada, Skype Empresarial Server solicitud de certificado va a usar la plantilla de certificado de servidor web. Si ha iniciado sesión con una cuenta que es miembro del grupo RTCUniversalServerAdmins para solicitar un certificado a través de esta plantilla, compruebe dos veces para asegurarse de que se ha asignado al grupo los permisos Inscribir para usar esa plantilla. 
  
### <a name="internal-edge-interface-certificates"></a>Certificados de interfaz perimetral interna

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. Descargar o exportar la cadena de certificación de CA

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp; a. Descargar con el sitio web certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Inicie sesión en un Skype Empresarial Server en la red interna como miembro del grupo administradores local.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. Abra **Inicio** y **Ejecutar** (o **Buscar** y **ejecutar)** y, a continuación, escriba lo siguiente:
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Por ejemplo:
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. En la página web certsrv de la ca emisora, en **Seleccionar** una tarea, haga clic en Descargar un certificado de CA, cadena de **certificados o CRL.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. En **Descargar un certificado de CA, cadena de certificados o CRL,** haga clic en Descargar cadena de certificados de **CA**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. En el cuadro **Descargar archivo,** haga clic **en Guardar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Guarde el archivo .p7b en la unidad de disco duro del servidor y, a continuación, cópielo en una carpeta en cada uno de los servidores perimetrales.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Exportar con MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Puede exportar el certificado raíz de ca desde cualquier máquina unida a un dominio mediante MMC. Vaya a **Inicio** y **ejecución** o abra **Búsqueda** y escriba **MMC** para abrir.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. En la consola MMC, haga clic **en Archivo** y, a continuación, haga clic en **Agregar o quitar complemento.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. En la **lista de diálogo Agregar o** quitar complementos, elija **Certificados** y, a continuación, haga clic en **Agregar**. Cuando se le pida, seleccione **Cuenta del** equipo y, a continuación, **Siguiente**. En el cuadro de diálogo **Seleccionar equipo**, seleccione **Equipo local**. Haga **clic en Finalizar** y, a continuación, en **Aceptar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. Expanda **Certificados (equipo local).** Expanda **Entidades de certificación raíz de confianza**. Seleccione **Certificados**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Haga clic en el certificado raíz emitido por su CA. Haga clic con el botón secundario en el certificado, **elija Todas** las tareas en el menú y, a continuación, **seleccione Exportar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Se **abrirá el Asistente para exportación de** certificados. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii. En el **cuadro de diálogo Exportar formato de** archivo, elija el formato al que desea exportar. Nuestra recomendación es **Cryptographic Message Syntax Standard - PKCS #7 Certificates (P7b)**. Si esa es su elección, recuerde también  seleccionar la casilla Incluir todos los certificados en la ruta de certificación si es posible, ya que esto también exportará la cadena de certificados, incluido el certificado de CA raíz y los certificados intermedios. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii. En el **cuadro de diálogo** Archivo para exportar, en la entrada nombre de archivo, escriba una ruta de acceso y un nombre de archivo (la extensión predeterminada sería .p7b) para el certificado exportado. Si es más fácil, elija  el botón Examinar para ir a la ubicación en la que desea guardar el certificado exportado y asigne un nombre al certificado exportado aquí. Haga **clic en** Guardar y, a continuación, en Siguiente cuando esté listo. 
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix. Revise el resumen de las acciones y haga clic **en Finalizar** para completar la exportación del certificado. Haga clic en **Aceptar** para confirmar si la exportación se ha completado correctamente.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Copie el archivo .p7b en cada uno de los servidores perimetrales.
    
### <a name="2-import-the-ca-certification-chain"></a>2. Importar la cadena de certificación de CA

&nbsp;&nbsp;&nbsp;a. En cada servidor perimetral, abra mmc (elija **Iniciar** y **ejecutar** o Buscar **y** escriba **MMC** para abrir).
    
&nbsp;&nbsp;&nbsp;b. En el **menú Archivo,** haga clic **en Agregar o** quitar complemento y, a continuación, elija **Agregar**.
    
&nbsp;&nbsp;&nbsp;c. En el **cuadro Agregar o quitar complementos,** haga clic en **Certificados** y, a continuación, haga clic en **Agregar**.
    
&nbsp;&nbsp;&nbsp;d. En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y, a continuación, haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;e. En el **cuadro de diálogo** Seleccionar equipo, asegúrese de que la casilla Equipo **local: (el** equipo en el que se ejecuta esta consola) está activada y, a continuación, haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;f. Haga **clic en** Cerrar y, a continuación, en **Aceptar**.
    
&nbsp;&nbsp;&nbsp;g. En el árbol de consola, expanda Certificados **(equipo local),** haga clic con el botón secundario en Entidades de certificación raíz de confianza **,** vaya a **Todas** las tareas y, a continuación, haga clic en **Importar**.
    
&nbsp;&nbsp;&nbsp;h. En el asistente que  aparece, en el cuadro de texto Archivo para importar, especifique el nombre de archivo del certificado (el nombre que dio al archivo .p7b en la sección anterior). Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;i. Deje el botón de radio en **Colocar todos los certificados en el siguiente almacén,** ya que deben seleccionarse las entidades de certificación raíz de confianza. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;j. Revise el resumen y haga clic **en Finalizar** para completar la importación.
    
&nbsp;&nbsp;&nbsp;k. Esto tendrá que hacerse para todos los servidores perimetrales que implemente.
    
### <a name="3-create-the-certificate-request"></a>3. Crear la solicitud de certificado

&nbsp;&nbsp;&nbsp;a. Inicie sesión en uno de los servidores perimetrales, inicie el Asistente para implementación y, en el paso **3: Solicitar,** instalar o asignar certificados, haga clic en Ejecutar **(o** Ejecutar de **nuevo,** si ya ha ejecutado este asistente).
    
&nbsp;&nbsp;&nbsp;b. En la **página Solicitud de** certificado, asegúrese de que el certificado perimetral **interno** está seleccionado y haga clic en **Solicitar**.
    
&nbsp;&nbsp;&nbsp;c. En la página Solicitudes retrasadas  o **inmediatas,** elija Enviar la solicitud inmediatamente a una entidad de certificación en línea si tiene acceso a una desde el entorno perimetral o Prepare la solicitud **ahora,** pero envíela más adelante de lo contrario.
    
&nbsp;&nbsp;&nbsp;d. En la **página Archivo de** solicitud de certificado, escriba la parte completa y el nombre del archivo donde se guardará el archivo (como c:\SkypeInternalEdgeCert.cer). Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;e. En la **página Especificar plantilla de** certificado alternativa, para usar una plantilla que no sea la plantilla predeterminada de WebServer, active la casilla Usar plantilla de certificado alternativa para la **entidad** de certificación seleccionada. De lo contrario, no haga nada.
    
&nbsp;&nbsp;&nbsp;f. En la página Nombre y configuración de seguridad, haga lo siguiente:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado (como Perímetro interno).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. En **Longitud de** bits, elija la longitud de bits (el valor predeterminado es 2048, puede ir más alto y ser más seguro, pero ralentizará el rendimiento).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. Si necesita un certificado exportable, debe marcar la casilla Marcar clave privada del certificado **como exportable.**
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;g. En la **página Información de** la organización, escriba el nombre de la organización y la unidad organizativa (OU). Puede escribir su división o departamento (TI, por ejemplo).
    
&nbsp;&nbsp;&nbsp;h. En la **página Información geográfica,** escriba la información de ubicación.
    
&nbsp;&nbsp;&nbsp;i. En la **página Nombre de sujeto/Nombres alternativos** de sujeto, el asistente debe rellenarlo automáticamente.
    
&nbsp;&nbsp;&nbsp;j. En la **página Configurar nombres alternativos de** sujeto adicionales, debe agregar los nombres alternativos de sujeto adicionales que necesite.
    
&nbsp;&nbsp;&nbsp;k. En la **página Resumen de solicitud,** consulte la información del certificado que se usará para generar la solicitud. Si necesita realizar cambios, vuelva atrás y haga esto ahora.
    
&nbsp;&nbsp;&nbsp;l. A **continuación,** haga clic en Siguiente para generar el archivo  CSR que necesitará proporcionar a la CA (también puede hacer clic en Ver registro para ver el registro de la solicitud de certificado).
    
&nbsp;&nbsp;&nbsp;m. Una vez generada la solicitud, puede hacer clic en **Ver** para ver el certificado y Finalizar **para** cerrar la ventana. El contenido del archivo CSR debe ser entregado a la ca, por lo que pueden generar un certificado para que se importe a este equipo en la siguiente sección.
    

### <a name="4-import-the-certificate"></a>4. Importar el certificado

&nbsp;&nbsp;&nbsp;a. Inicie sesión, como miembro del grupo administradores local, en el servidor perimetral desde el que realizó la solicitud de certificado en el último procedimiento.
    
&nbsp;&nbsp;&nbsp;b. En el Asistente para implementación, junto al **paso 3. Request, Install or Assign Certificates**, click **Run Again**.
    
&nbsp;&nbsp;&nbsp;c. En la **página Tareas de certificados disponibles,** haga clic en Importar un certificado de un archivo **. Archivo P7b, .pfx o .cer**.
    
&nbsp;&nbsp;&nbsp;d. En la **página** Importar certificado, escriba la ruta de acceso completa y el  nombre de archivo del certificado que obtuvo en la sección anterior (o puede hacer clic en Examinar para buscar y elegir el archivo de esa manera).
    
&nbsp;&nbsp;&nbsp;e. Si va a importar certificados para otros miembros del grupo de servidores perimetrales y  el certificado contiene una clave privada, asegúrese de seleccionar la casilla Archivo de certificado que contiene la clave privada del certificado y especifique la contraseña. Haga clic en **Siguiente** para continuar.
    
&nbsp;&nbsp;&nbsp;f. En la **página Resumen,** haga clic en **Siguiente**  una vez que haya confirmado la información y Finalizar una vez que el certificado se importe correctamente.
    
 
### <a name="5-export-the-certificate"></a>5. Exportar el certificado

&nbsp;&nbsp;&nbsp;a. Asegúrese de que ha iniciado sesión en el servidor perimetral al que importó el certificado anteriormente, como miembro del grupo administradores local.
    
&nbsp;&nbsp;&nbsp;b. Haga **clic en** Inicio , **Ejecutar** (o abra **Búsqueda)** y escriba **MMC**.
    
&nbsp;&nbsp;&nbsp;c. En la consola MMC, haga clic **en Archivo** y haga clic **en Agregar o quitar complemento.**
    
&nbsp;&nbsp;&nbsp;d. En el **cuadro Agregar o quitar complementos,** haga clic en **Certificados** y haga clic en **Agregar**.
    
&nbsp;&nbsp;&nbsp;e. En el **cuadro de diálogo Complemento** Certificados, elija Cuenta de **equipo**. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En el **cuadro de diálogo** Seleccionar equipo, seleccione Equipo **local: (el equipo** en el que se ejecuta esta consola). Haga clic en **Finalizar**. Haga **clic en** Aceptar y se completa la configuración de la consola mmc.
    
&nbsp;&nbsp;&nbsp;g. Haga doble clic en **Certificados (equipo local)** para ampliar los almacenes de certificados. Haga doble clic en **Personal** y, a continuación, haga clic **en Certificados**.
    
  > [!NOTE]
  > Puede que esté aquí y no verá ningún certificado en el almacén de certificados personales del equipo local. No es necesario buscar alrededor, si la clave no está ahí, el certificado importado no tenía una clave privada asociada. Pruebe la solicitud e importe los pasos anteriores una vez más y, si está seguro de que tiene todo lo correcto, consulte a su administrador o proveedor de ca. 
  
&nbsp;&nbsp;&nbsp;h. En el **almacén personal de certificados** para el equipo local, haga clic con el botón secundario en el certificado que está exportando. Seleccione **Todas las tareas** en el menú resultante y, a continuación, haga clic en **Exportar**.
    
&nbsp;&nbsp;&nbsp;i. En el **Asistente para exportación de certificados**, haga clic en **Siguiente**. Seleccione **Sí, exporte la clave privada**. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;j. En el **cuadro de diálogo** Exportar formatos de archivo, seleccione Personal Information Exchange - **PKCS#12 (. PFX)** y, a continuación, seleccione lo siguiente:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Incluya todos los certificados en la ruta de certificación, si es posible.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii. Exporte todas las propiedades extendidas.
    
   > [!NOTE]
   > **NUNCA** seleccione **Eliminar la clave privada si la exportación se realiza correctamente.** Significará que tendrá que volver a importar el certificado y la clave privada a este servidor perimetral.
  
&nbsp;&nbsp;&nbsp;k. Si desea asignar una contraseña para proteger la clave privada, puede escribir una contraseña para la clave privada. Vuelva a escribir la contraseña para confirmar y, a continuación, haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;l. Escriba una ruta de acceso y un nombre de archivo para el certificado exportado, con una extensión de archivo **de .pfx**. Los demás servidores perimetrales del grupo deben tener acceso a la ruta de acceso o deberá mover el archivo mediante medios externos (como una unidad USB). Haz **clic en** Siguiente cuando hayas elegido.
    
&nbsp;&nbsp;&nbsp;m. Revise el resumen del cuadro de diálogo **Completar el Asistente para** exportación de certificados y, a continuación, haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;n. Haga clic en **Aceptar** cuando el cuadro de diálogo informe de que la exportación ha concluido correctamente
    
 
### <a name="6-assign-the-certificate"></a>6. Asignar el certificado

&nbsp;&nbsp;&nbsp;a. En CADA servidor perimetral, en el Asistente para implementación, junto al **paso 3. Request, Install or Assign Certificates**, click **Run again**.
    
&nbsp;&nbsp;&nbsp;b. En la **página Tareas de certificados disponibles,** haga clic en Asignar un certificado **existente.**
    
&nbsp;&nbsp;&nbsp;c. En la página **Asignación del certificado**, seleccione **Interfaz perimetral interna** en la lista.
    
&nbsp;&nbsp;&nbsp;d. En la **página Almacén de** certificados, seleccione el certificado que ha importado para el servidor perimetral interno (en la sección anterior).
    
&nbsp;&nbsp;&nbsp;e. En la **página Resumen de asignación de** certificados, busque la configuración y, a continuación, haga clic en **Siguiente** para asignar el certificado.
    
&nbsp;&nbsp;&nbsp;f. En la página de finalización del asistente, haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;g. Una vez completado este procedimiento, es una buena idea abrir el complemento MMC certificados en cada servidor perimetral, expandir Certificados  **(equipo local),** expandir **Personal**, hacer clic en Certificados y confirmar que el certificado perimetral interno aparece en el panel de detalles.
    
### <a name="external-edge-interface-certificates"></a>Certificados de interfaz perimetral externa

 
### <a name="1-create-the-certificate-request"></a>1. Crear la solicitud de certificado

&nbsp;&nbsp;&nbsp;a. Inicie sesión en uno de los servidores perimetrales, inicie el Asistente para implementación y, en el paso **3: Solicitar,** instalar o asignar certificados, haga clic en Ejecutar (o Ejecutar de **nuevo,** si ya ha ejecutado este asistente).
    
&nbsp;&nbsp;&nbsp;b. En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.
    
&nbsp;&nbsp;&nbsp;c. En la **página Solicitud de** certificado, asegúrese de que el certificado perimetral **externo** está seleccionado y haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;d. En la página **Solicitudes retrasadas o inmediatas**, haga clic en **Prepare ahora la solicitud, pero envíela más tarde**.
    
&nbsp;&nbsp;&nbsp;e. En la **página Archivo de** solicitud de certificado, escriba la parte completa y el nombre del archivo donde se guardará el archivo (como c:\SkypeInternalEdgeCert.cer). Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En la **página Especificar plantilla de** certificado alternativa, para usar una plantilla que no sea la plantilla predeterminada de WebServer, active la casilla Usar plantilla de certificado alternativa para la **entidad** de certificación seleccionada.
    
&nbsp;&nbsp;&nbsp;g. En la página Nombre y configuración de seguridad, haga lo siguiente:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado (como Borde externo).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. En **Longitud de** bits, elija la longitud de bits (el valor predeterminado es 2048, puede ir más alto y ser más seguro, pero ralentizará el rendimiento).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. Si necesita un certificado exportable, debe marcar la casilla Marcar clave privada del certificado **como exportable.**
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;h. En la **página Información de** la organización, escriba el nombre de la organización y la unidad organizativa (OU). Puede escribir su división o departamento (TI, por ejemplo).
    
&nbsp;&nbsp;&nbsp;i. En la **página Información geográfica,** escriba la información de ubicación.
    
&nbsp;&nbsp;&nbsp;j. En la **página Nombre de sujeto/Nombres alternativos** de sujeto, el asistente debe rellenar automáticamente la información necesaria.
    
&nbsp;&nbsp;&nbsp;k. En la página Configuración de dominio SIP en nombres alternativos de sujeto **(SAN),** active la casilla dominio para agregar un sip.<sipdomain> entrada a la lista de nombres alternativos de sujeto.
    
&nbsp;&nbsp;&nbsp;l. En la **página Configurar nombres alternativos de** sujeto adicionales, debe agregar los nombres alternativos de sujeto adicionales que necesite.
    
&nbsp;&nbsp;&nbsp;m. En la **página Resumen de solicitud,** consulte la información del certificado que se usará para generar la solicitud. Si necesita realizar cambios, vuelva atrás y haga esto ahora.
    
&nbsp;&nbsp;&nbsp;n. Cuando esté listo,  haga clic en Siguiente para generar el archivo CSR que  deberá proporcionar a la CA (también puede hacer clic en Ver registro para ver el registro de la solicitud de certificado).
    
&nbsp;&nbsp;&nbsp;o. Una vez generada la solicitud, puede hacer clic en **Ver** para ver el certificado y Finalizar **para** cerrar la ventana. El contenido del archivo CSR debe ser entregado a la ca, por lo que pueden generar un certificado para que se importe a este equipo en la siguiente sección.
    
&nbsp;&nbsp;&nbsp;p. (OPCIONAL) Es posible que, al enviar el contenido de la CSR, se le pida cierta información, como se muestra a continuación (las CA varían mucho, por lo que puede que esto no sea necesario):
    
  - **Microsoft** como plataforma de servidor
    
  - **IIS** como versión
    
  - **Servidor web** como tipo de uso
    
  - **PKCS7 como** formato de respuesta
    
 
### <a name="2-import-the-certificate"></a>2. Importar el certificado

&nbsp;&nbsp;&nbsp;a. Inicie sesión, como miembro del grupo administradores local, en el servidor perimetral desde el que realizó la solicitud de certificado en el último procedimiento.
    
&nbsp;&nbsp;&nbsp;b. En el Asistente para implementación, junto al **paso 3. Request, Install or Assign Certificates**, click **Run Again**.
    
&nbsp;&nbsp;&nbsp;c. En la **página Tareas de certificados disponibles,** haga clic en Importar un certificado de un archivo **. Archivo P7b, .pfx o .cer**.
    
&nbsp;&nbsp;&nbsp;d. En la **página** Importar certificado, escriba la ruta de acceso completa y el  nombre de archivo del certificado que obtuvo en la sección anterior (o puede hacer clic en Examinar para buscar y elegir el archivo de esa manera). Si el certificado contiene una clave privada, asegúrese de seleccionar Archivo de certificado contiene la clave privada del certificado y escriba la contraseña de la clave privada. Haga **clic en Siguiente** cuando esté listo.
    
&nbsp;&nbsp;&nbsp;e. En la **página Importar resumen de certificado,** revise la información de resumen y haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En la **página Ejecutar comandos,** puede revisar el resultado de la importación cuando se complete haciendo clic en **Ver registro**. Haga **clic en** Finalizar para completar la importación de certificados.
    
&nbsp;&nbsp;&nbsp;g. Si tiene otros servidores perimetrales en un grupo de servidores, también tendrá que seguir los dos procedimientos siguientes. Si se trata de un servidor perimetral independiente, ha terminado con certificados externos.
    
 
### <a name="3-export-the-certificate"></a>3. Exportar el certificado

&nbsp;&nbsp;&nbsp;a. Asegúrese de que ha iniciado sesión en el servidor perimetral al que importó el certificado como administrador local.
    
&nbsp;&nbsp;&nbsp;b. Haga **clic en** Inicio , **Ejecutar** (o abra **Búsqueda)** y escriba **MMC**.
    
&nbsp;&nbsp;&nbsp;c. En la consola MMC, haga clic **en Archivo** y, a continuación, haga clic en **Agregar o quitar complemento**.
    
&nbsp;&nbsp;&nbsp;d. En el **cuadro Agregar o quitar complementos,** haga clic en **Certificados** y haga clic en **Agregar**.
    
&nbsp;&nbsp;&nbsp;e. En el **cuadro de diálogo Complemento** Certificados, elija Cuenta de **equipo**. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En el **cuadro de diálogo** Seleccionar equipo, seleccione Equipo **local: (el equipo** en el que se ejecuta esta consola). Haga clic en **Finalizar**. Haga **clic en** Aceptar y se completa la configuración de la consola mmc.
    
&nbsp;&nbsp;&nbsp;g. Haga doble clic en **Certificados (equipo local)** para ampliar los almacenes de certificados. **Haga doble clic en Personal** y, a continuación, haga clic en **Certificados**.
    
   > [!NOTE]
   > Puede que esté aquí y no verá ningún certificado en el almacén de certificados personales del equipo local. No es necesario buscar alrededor, si la clave no está ahí, el certificado importado no tenía una clave privada asociada. Pruebe la solicitud e importe los pasos anteriores una vez más y, si está seguro de que tiene todo lo correcto, consulte a su administrador o proveedor de ca. 
  
&nbsp;&nbsp;&nbsp;h. En el **almacén personal de certificados** para el equipo local, haga clic con el botón secundario en el certificado que está exportando. **Seleccione Todas las tareas** en el menú resultante y, a continuación, haga clic en **Exportar**.
    
&nbsp;&nbsp;&nbsp;i. En el **Asistente para exportación de certificados**, haga clic en **Siguiente**. Seleccione **Sí, exporte la clave privada**. Haga clic en **Siguiente**.
    
   > [!NOTE]
   > Si **es Así, la** exportación de la clave privada no está disponible, la clave privada de este certificado no se marcó para su exportación antes de obtenerla. Debe solicitar el certificado al proveedor de nuevo, con la clave privada establecida para exportar, antes de hacerlo correctamente.
  
&nbsp;&nbsp;&nbsp;j. En el cuadro de diálogo Exportar formatos de archivo, seleccione Personal Information Exchange - PKCS#12 (. PFX) y, a continuación, seleccione lo siguiente:
    
 &nbsp;&nbsp;&nbsp;  i. Incluya todos los certificados en la ruta de certificación, si es posible.
    
 &nbsp;&nbsp;&nbsp;  ii. Exporte todas las propiedades extendidas.
    
   > [!NOTE]
   > **NUNCA** seleccione **Eliminar la clave privada si la exportación se realiza correctamente.** Significará que tendrá que volver a importar el certificado y la clave privada a este servidor perimetral.
  
&nbsp;&nbsp;&nbsp;k. Si desea asignar una contraseña para proteger la clave privada, puede escribir una contraseña para la clave privada. Vuelva a escribir la contraseña para confirmar y, a continuación, haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;l. Escriba una ruta de acceso y un nombre de archivo para el certificado exportado, con una extensión de archivo **de .pfx**. Los demás servidores perimetrales del grupo deben tener acceso a la ruta de acceso o deberá mover el archivo mediante medios externos (como una unidad USB). Haz **clic en** Siguiente cuando hayas elegido.
    
&nbsp;&nbsp;&nbsp;m. Revise el resumen del cuadro de diálogo **Completar el Asistente para** exportación de certificados y, a continuación, haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;n. Haga clic en **Aceptar** cuando el cuadro de diálogo informe de que la exportación ha concluido correctamente
    
&nbsp;&nbsp;&nbsp;o. Ahora tendrá que volver a la sección Importar el certificado antes de esto e importar el certificado a todos los servidores perimetrales restantes y luego continuar con la asignación, a continuación.
    
 
### <a name="4-assign-the-certificate"></a>4. Asignar el certificado

&nbsp;&nbsp;&nbsp;a. En **CADA** servidor perimetral, en el Asistente para implementación, junto al **paso 3. Request, Install or Assign Certificates**, click **Run again**.
    
&nbsp;&nbsp;&nbsp;b. En la **página Tareas de certificados disponibles,** haga clic en Asignar un certificado **existente.**
    
&nbsp;&nbsp;&nbsp;c. En la **página Asignación de** certificados, seleccione **Externo perimetral** en la lista.
    
&nbsp;&nbsp;&nbsp;d. En la **página Almacén de** certificados, seleccione el certificado que ha importado para el servidor perimetral externo (en la sección anterior).
    
&nbsp;&nbsp;&nbsp;e. En la **página Resumen de asignación de** certificados, busque la configuración y, a continuación, haga clic en **Siguiente** para asignar el certificado.
    
&nbsp;&nbsp;&nbsp;f. En la página de finalización del asistente, haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;g. Una vez completado este procedimiento, es una buena idea abrir el complemento MMC certificados en cada servidor, expandir Certificados  **(equipo local),** expandir **Personal**, hacer clic en Certificados y confirmar que el certificado perimetral interno aparece en el panel de detalles.
    
   > [!NOTE]
   > También tendrá que configurar los certificados para el servidor proxy inverso. 
  
## <a name="starting-the-edge-servers"></a>Inicio de los servidores perimetrales

Una vez completada la instalación, deberá iniciar los servicios en cada servidor perimetral de la implementación:
  
1. En cada servidor perimetral, en **el** Asistente para implementación , junto al **Paso 4: Iniciar servicios**, haga clic en **Ejecutar**.
    
2. En la **página Skype Empresarial Server servicios,** revise la lista de servicios y, a continuación, haga clic en **Siguiente** para iniciar los servicios.
    
3. Una vez iniciados los servicios, puede hacer clic **en Finalizar** para cerrar el asistente.
    
4. (Opcional) Todavía en **paso 4: Iniciar servicios**, haga clic en Estado de **servicios**.
    
5.  En la **MMC de servicios** de cada servidor, compruebe que todos los Skype Empresarial Server se están ejecutando.
    

