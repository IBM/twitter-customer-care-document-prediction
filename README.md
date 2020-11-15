# Twitter Conversations Dataset for Conversational Document Prediction

## Dataset
This directory contains the Twitter Conversations dataset that we release for the task of Conversational Document Prediction.  

The dataset includes conversations that occurred between users and customer care agents in 25 organizations on the Twitter platform. Each conversation ends with a customer care agent providing a URL to a document to resolve the issue the user is facing. The task is to predict the document given a dialog context.  

Following files are included in the dataset.

| File  | Description  |
|-------|--------------|
| train.json  | Training dataset  |
| dev.json  |  Validation dataset |
| test.json  |  Test dataset |
| docID_content.tsv  | The content of the documents indexed by the document ID  |
| docID_url.tsv  | The URLs of the documents indexed by the document ID  |
| company_docIDs.tsv  | The document IDs corresponding to each organization.  |

  
The train, dev and test datasets include 10000, 525 and 500 conversations respectively.

## Example
Following data format is followed by each conversation in train, dev and test datasets.

```json
{
        "agentURL": {
            "doc_id": "9417",
            "turn": "4",
            "tweet_ID": "1232360458130161664",
            "url": "https://support.rockstargames.com/articles/204233943/Basic-Troubleshooting-for-the-PlayStation-4-Console",
            "url_utterance": "@tiffamy_lee We have a Support article that may help with that. Please see: https://support.rockstargames.com/articles/204233943/Basic-Troubleshooting-for-the-PlayStation-4-Console *SR"
        },
        "dialogContent": [
            {
                "client": "tiffamy_lee",
                "datetime": "2020-02-25T17:40:50.000Z",
                "message": "@RockstarSupport why isnt my gta installing at all ?",
                "tweet_ID": "1232359814828822534"
            },
            {
                "agent": "RockstarSupport",
                "datetime": "2020-02-25T17:41:59.000Z",
                "message": "@tiffamy_lee Please let us know the platform you are experiencing this on so we can help further. *SR",
                "tweet_ID": "1232360105036984320"
            },
            {
                "client": "tiffamy_lee",
                "datetime": "2020-02-25T17:42:23.000Z",
                "message": "@RockstarSupport Playstation 4",
                "tweet_ID": "1232360202671968257"
            }
        ],
        "dialogHeader": {
            "company": "RockstarSupport",
            "conversationDateTime": "2020-02-25T17:40:50.000Z",
            "duration": "00:08:46.0",
            "messageCount": "4",
            "sessionID": "5McvPTUPveowZZ4Z9j5Y"
        }
    }
```

Each conversation contains 3 fields.  

1. `dialogHeader` – Contains general information about the conversation. This include, organization name, number of messages in the conversation and a unique session ID given to the conversation.  

2. `dialogContent` – Contains the utterances prior to the agent responding with a URL to a document. Each utterance includes information such as the agent/user name, date and time of the utterance, the tweet ID corresponding to the utterance and the text of the utterance.  

3. `agentURL` – This includes information regarding the last agent utterance which contain an URL to a document. This contains the tweet ID of the agent utterance, the text of the utterance that contains the URL, the URL extracted from the utterance and the document ID of the URL. The content of the provided document can be obtained by referring to the ‘docID_content.tsv’ with the doc_id provided in this field.  

## Statistics
Main statistics of the dataset are provided supplementary to the dataset in the directory `stats`.

## Data Collection
A set of 25 organizations which conduct customer care operations in Twitter platform were identified. Then, the user_timeline Twitter API was used to collect the tweets from these organizations containing in-domain URLs. The dialogs were constructed starting from these tweets and identifying the previous user and agent tweets to these tweets.

## Public data release
During the public data release, adhering to the Twitter Developer policy for Content Redistribution, we will be releasing the Tweet IDs of each Tweet in a conversation and the Code for retrieving the actual tweet given the Tweet ID. We will also be releasing the code to obtain content from the URLs used in the conversations.

## License

The dataset is released under [**Apache 2.0**](https://www.apache.org/licenses/LICENSE-2.0) license. For the full
license, see [LICENSE](LICENSE). Please cite the following paper if you
use this dataset in your work

```shell
@inproceedings{ganhotra-etal-2020-conversational,
    title = "Conversational Document Prediction to Assist Customer Care Agents",
    author = "Ganhotra, Jatin  and
      Roitman, Haggai  and
      Cohen, Doron  and
      Mills, Nathaniel  and
      Gunasekara, Chulaka  and
      Mass, Yosi  and
      Joshi, Sachindra  and
      Lastras, Luis  and
      Konopnicki, David",
    booktitle = "Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP)",
    month = nov,
    year = "2020",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/2020.emnlp-main.25",
    pages = "349--356",
}
```


## Dataset Metadata
The following table is necessary for this dataset to be indexed by search
engines such as <a href="https://g.co/datasetsearch">Google Dataset Search</a>.
<div itemscope itemtype="http://schema.org/Dataset">
<table>
  <tr>
    <th>property</th>
    <th>value</th>
  </tr>
  <tr>
    <td>name</td>
    <td><code itemprop="name">Twitter Conversations Dataset for Conversational Document Prediction (CDP) task</code></td>
  </tr>
  <tr>
    <td>alternateName</td>
    <td><code itemprop="alternateName">Twitter CDP dataset</code></td>
  </tr>
  <tr>
    <td>url</td>
    <td><code itemprop="url">https://github.com/IBM/twitter-customer-care-document-prediction</code></td>
  </tr>
  <tr>
    <td>sameAs</td>
    <td><code itemprop="sameAs">https://github.com/IBM/twitter-customer-care-document-prediction</code></td>
  </tr>
  <tr>
    <td>description</td>
    <td><code itemprop="description">The dataset contains the Twitter Conversations for the task of Conversational Document Prediction (CDP). The dataset includes conversations that occurred between users and customer care agents in 25 organizations on the Twitter platform. Each conversation ends with a customer care agent providing a URL to a document to resolve the issue the user is facing. The task is to predict the document given a dialog context. </code></td>
  </tr>
  <tr>
    <td>provider</td>
    <td>
      <div itemscope itemtype="http://schema.org/Organization" itemprop="provider">
        <table>
          <tr>
            <th>property</th>
            <th>value</th>
          </tr>
          <tr>
            <td>name</td>
            <td><code itemprop="name">IBM</code></td>
          </tr>
          <tr>
            <td>sameAs</td>
            <td><code itemprop="sameAs">https://en.wikipedia.org/wiki/IBM</code></td>
          </tr>
        </table>
      </div>
    </td>
  </tr>
  <tr>
    <td>citation</td>
    <td><code itemprop="citation">https://www.aclweb.org/anthology/2020.emnlp-main.25</code></td>
  </tr>
</table>
</div>