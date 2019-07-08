# Errors

The errors may be printed in different situations
They contain:
- Code - The code starts with the initials of the error context, example: DBA_1 which belongs to DBA context.
- Message - The message of the error.
- Field - Additional info.
- Variable - Additional info.
- Data - Additional info.

#### Example of response
```
{
  errorCode: "DBA_7",
  field: "account",
  message: "Conta é obrigatória e deve conter entre 7 e 8 números"
}
```

## Errors
**Some error codes have more than one message, these multiple error messages will be removed until august 12th leaving all errors with only one message**

| Code     | message                                                                                         |
|----------|-------------------------------------------------------------------------------------------------|
| DBA_1    | "Dígito da agência é obrigatório e deve ser numérico ou x"                                      |
| DBA_2    | "Dígito da conta é obrigatório e deve ser numérico ou x"                                        |  
| DBA_3    | "Agência deve ser 1" or "Agência inválida"                                                      |
| DBA_4    | "Agência é obrigatória e deve conter no máximo {{maxLength}} números"                           |
| DBA_5    | "Dígito da agência deve ter apenas 1 dígito"                                                    |
| DBA_6    | "Conta é obrigatória e deve conter no máximo {{maxLength}} números"                             |
| DBA_7    | "Conta é obrigatória e deve conter entre {{minLength}} e {{maxLength}} números"                 |
| DBA_8    | "Dígito da Conta é obrigatório e deve ter apenas 1 dígito"                                      |
| DBA_9    | "Conta do banco é obrigatória e deve conter exatamente {{exactLength}} números"                 |
| DBA_10   | "Tipo de conta inválido", "Tipo da conta inválido." or "Tipo da conta do favorecido inválido."  |
| DBA_11   | "Tipo de conta 'Entidade pública' é disponível somente para CNPJ" or                            | 
|          | "Tipo de conta \'Entidade pública\' só permite pessoa jurídica."                                |
| DBA_12   | "Documento do favorecido não é um CPF nem CNPJ", "CPF/CNPJ é obrigatório" or                    |
|          | "Documento {{document}} não é um CPF ou CNPJ"                                                   |
| DBA_13   | "O CPF ou CNPJ está bloqueado", "Documento {{document}} está bloqueado"                         |
| DBA_15   | "O nome deve ter no mínimo 2 palavras" or "Nome completo é obrigatório"                         |
| DBA_19   | "Dígito da Agência não é válido"                                                                |
| DBA_20   | "Conta ou dígito verificador da conta inválido.",                                               |
|          | "Agência, tipo da conta, conta ou dígito verificador da conta inválido.",                       |
|          | "Dígito verificador da conta inválido.",                                                        |
|          | "Agência, Conta ou dígito verificador da conta inválido." or                                    |
|          | "Agência, conta ou dígito verificador da conta inválido."                                       |
| DBA_21   | "Conta inválida."                                                                               |
| DBA_22   | "Agência não existe"                                                                            |
| DBA_23   | "Documento não existe",                                                                         |
| DBA_24   | "Nome informado não coincide com o nome no Documento"                                           |
| DBA_26   | "Conta inválida. O inicio da conta {{accountBeginning}} não é reconhecido como um tipo válido." |
| DBA_27   | "CNPJ {{document}} inválido"                                                                    |
| DBA_28   | "CPF {{document}} inválido"                                                                     |
