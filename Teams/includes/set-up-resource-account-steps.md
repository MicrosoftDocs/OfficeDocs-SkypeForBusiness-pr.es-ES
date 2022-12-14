En Microsoft Teams, es necesaria una cuenta de recursos para cada operador automático o cola de llamadas. Las cuentas de recursos también pueden tener asignados números de teléfono. Así se asignan números de teléfono a operadores automáticos y colas de llamadas, lo que permite a los autores de llamadas de fuera de Teams ponerse en contacto con el operador automático o la cola de llamadas.

Este artículo trata sobre cómo crear cuentas de recursos y prepararlas para su uso con operadores automáticos y colas de llamadas.

Antes de empezar los procedimientos de este artículo, asegúrese de que ha realizado los pasos siguientes:

- [Obtener licencias de cuenta de recursos Teléfono Microsoft Teams](#obtain-microsoft-teams-phone-resource-account-licenses)
- [Obtener números de teléfono](#obtain-phone-numbers)

> [!NOTE]
> Las cuentas de recursos usadas para operadores automáticos y colas de llamadas están deshabilitadas para iniciar sesión y deben permanecer así. El chat y la presencia no están disponibles para estas cuentas.

### <a name="obtain-microsoft-teams-phone-resource-account-licenses"></a>Obtener licencias de cuenta de recursos Teléfono Microsoft Teams

Cada cuenta de recursos requiere una licencia para trabajar con operadores automáticos y colas de llamadas, lo que se conoce como una licencia de **cuenta de recursos de Teléfono Microsoft Teams**. Las suscripciones con Teams Phone obtienen automáticamente una asignación gratuita de licencias de **Teléfono Microsoft Teams cuenta** de recursos y, si se necesitan más, se pueden comprar licencias de cuenta de recursos **Teléfono Microsoft Teams** adicionales. Para obtener más información sobre cómo obtener estas licencias, consulte [Teléfono Microsoft Teams licencias de cuenta de recursos](../teams-add-on-licensing/virtual-user.md).

Explicamos cómo [asignar la licencia a una cuenta de recursos más adelante en este artículo](#assign-a-license).

Si compró **Teléfono Teams Estándar** o **Teams Phone con** licencias de paquetes de planes de llamadas, las licencias de la cuenta de recursos de **Teams Phone** ya están en su cuenta.

Para ver si ya tiene licencias de la cuenta de recursos de **Teams Phone**, inicie sesión en la [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339) con una cuenta con permisos de administrador global. A continuación, ve a [Facturación > Tus productos](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Si tiene licencias de **cuenta de recursos de Teléfono de Teams**, aparecerán como **Teléfono Microsoft Teams cuenta de recursos**.

1. Abra la [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339) e inicie sesión con un usuario que sea administrador global. Esta suele ser la cuenta que usaste para registrarte en Microsoft 365.
2. En el panel de navegación izquierdo, ve a **Complementos** >  de servicios  >  de [**compra** **de facturación** > ](https://admin.microsoft.com/Adminportal/Home#/catalog)**Ver todos los productos de complementos**.
3. Desplácese hasta el final para buscar la licencia **Teléfono Microsoft Teams cuenta de recursos**. Selecciona **Detalles** y, a continuación, **Comprar**.
4. En la página de compra de licencias, seleccione el número de licencias que desee. Necesita una licencia para cada operador automático y cola de llamadas que planee configurar. Se recomienda seleccionar al menos cinco licencias para que pueda configurar fácilmente más operadores automáticos y colas de llamadas en el futuro sin tener que comprar más licencias inmediatamente.
5. Desactive **Asignar automáticamente a todos los usuarios sin licencias**.
6. Selecciona **Echar un vistazo ahora**.
7. Confirma el pedido, selecciona **Siguiente** y, a continuación, **Realizar pedido**.

No hay ningún costo, pero aún debe seguir estos pasos para adquirir la licencia.

### <a name="obtain-phone-numbers"></a>Obtener números de teléfono

Los números de teléfono son opcionales para operadores automáticos y colas de llamadas. Para cualquier operador automático o cola de llamadas al que desee que un número de teléfono le pueda contactar directamente, debe tener una cuenta de recurso con un número de teléfono asociado.

Las cuentas de recursos pueden usar números de teléfono de pago o gratuitos. Puede solicitar números nuevos o transferir números existentes de otro operador.

Entre los números de teléfono aceptables que se pueden aplicar a las cuentas de recursos se incluyen:

- **Números de servicio de planes de llamadas:** Para adquirir números de servicio con planes de llamadas, consulte [Obtener números de teléfono de servicio](../getting-service-phone-numbers.md).
- **Números de enrutamiento directo:** Para adquirir los números de Enrutamiento directo, consulte [Habilitar el enrutamiento directo a los usuarios](/microsoftteams/direct-routing-enable-users#configure-the-phone-number-and-enable-enterprise-voice).
- **Operador Conectar números:** Para adquirir números de Operador Connect, consulta [Configurar operador conectar](/microsoftteams/operator-connect-configure#set-up-phone-numbers).

Para realizar la portabilidad de un número de otro operador, consulte [Transferir números de teléfono a Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Crear una cuenta de recursos

Puede crear una cuenta de recursos en el Centro de administración de Teams.

1. Inicie sesión en el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851). 
2. Expanda **Voz** y, después, seleccione **Cuentas de recursos**.
3. Seleccione **Agregar**.
4. En el panel **Agregar cuenta de recurso** , rellene **Nombre para mostrar**, **Nombre de usuario** y el **tipo de cuenta de recurso**. El tipo de cuenta de recurso puede ser **Operador automático** o **Cola de llamadas**, dependiendo de cómo desee usar esta cuenta de recursos.
5. Seleccione **Guardar**.

## <a name="assign-a-license"></a>Asignar una licencia

Para cada cuenta de recursos, debe asignar una licencia **de cuenta de recursos de Teléfono Microsoft Teams**.

1. Inicia sesión en la [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). 
2. Expanda **Usuarios** y, a continuación, seleccione **Usuarios activos**.
3. Seleccione la cuenta de recursos a la que desea asignar una licencia. Aparecerá el panel de usuario de la cuenta de recursos.
4. En la pestaña **Licencias y aplicaciones**, en **Licencias**, seleccione **Teléfono Microsoft Teams cuenta de recursos**.
5. Seleccione **Guardar cambios**.

## <a name="assign-a-phone-number"></a>Asignar un número de teléfono

Si está pensando en usar la cuenta de recursos con un operador automático o una cola de llamadas que requiera un número de teléfono, asigne un número a la cuenta del recurso.

1. Inicie sesión en el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. Expanda **Voz** y, a continuación, seleccione **Página de cuentas de recursos** .
3. Seleccione la cuenta de recursos a la que desea asignar un número de teléfono y, a continuación, seleccione **Asignar o anular la asignación**.
4. En la lista desplegable **Tipo de número** de teléfono, elija el tipo de número que desea usar.
5. En el cuadro **Número de teléfono asignado** , busque el número que desea usar y seleccione **Agregar**. Asegúrese de incluir el código de país (por ejemplo, +1 250 555 0012).
6. Seleccione **Guardar**.

Para asignar un número de enrutamiento directo o híbrido a una cuenta de recursos, debe usar PowerShell:

```powershell
Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting
```
