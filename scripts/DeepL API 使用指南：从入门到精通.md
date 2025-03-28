
DeepL 被广泛认为是目前最精准的机器翻译工具之一。为了提升翻译效率，我们可以通过调用其 API 实现自动化翻译流程。


1. **订阅类型选择**  
   DeepL 提供两种订阅模式：
   - DeepL Pro（个人版）
   - DeepL API（开发者版）

   **重要提示**：这两种订阅互斥，开通前请确认您需要的是 API 版本。

2. **获取 API Token**  
   订阅成功后，在账户设置中可获取专属的 API 认证密钥。

👉 [【点击获取】 Deepl PRO 高级会员独享30天（专业版） ](https://bit.ly/DEepl)


不同订阅等级使用不同的 API 端点：
- 免费版：`https://api-free.deepl.com`
- 专业版：`https://api.deepl.com`


通过词汇表(glossary)可以自定义专业术语翻译，显著提升翻译质量。


bash
TOKEN="your-token"

data=$(jq -n --arg glossary "$(cat glossary.tsv)" \
      '{
         name: "My Glossary",
         source_lang: "en",
         target_lang: "zh",
         entries: $glossary,
         entries_format: "tsv"
       }')

curl -X POST "https://api.deepl.com/v2/glossaries" \
--header "Authorization: DeepL-Auth-Key $TOKEN" \
--header "Content-Type: application/json" \
--data "$data"


- **查询所有词汇表**：
bash
curl -X GET "https://api.deepl.com/v2/glossaries" \
--header "Authorization: DeepL-Auth-Key $TOKEN"

- **查看具体条目**：
bash
curl -X GET "https://api.deepl.com/v2/glossaries/96ebcd10-ac05-4e43-a529-8e4bdc0d8dd2/entries" \
--header "Authorization: DeepL-Auth-Key $TOKEN" \
--header "Accept: text/tab-separated-values" \
-o glossary.tsv

- **删除词汇表**：
bash
curl -X DELETE "https://api.deepl.com/v2/glossaries/{glossary_id}" \
--header "Authorization: DeepL-Auth-Key $TOKEN"


1. 目前词汇表仅支持 TSV 和 CSV 格式
2. CSV 格式仅支持上传，不支持下载
3. 可先通过环境变量方式加载词汇表：`GLOSSARY=$(<glossary.tsv)`
4. 查询支持的语言对：
bash
curl -X GET "https://api.deepl.com/v2/glossary-language-pairs" \
--header "Authorization: DeepL-Auth-Key $TOKEN" | jq

通过合理使用这些功能，您可以打造出专业级的自动化翻译工作流。
