# Fraud-detection
	The project is to find the fraudulent transactions happen in e commerce website. This will help the business not to run into losses.
	The data is collected and stored in JSON profiles representing fictional customers from an e-commerce company. The profiles contain information about the customer, their orders, their transactions, what payment methods they used and whether the customer is fraudulent or not.

	Probelm statement:
		Parse the json data to columns and rows.
		Model building target variable(Fradulent)
		Report on model success and important features.
 
# Data Processing
		Refer customerdata.json for raw data of customers
		Refer Preprocessing.ipnyb for detailed steps of preprocessing.
		Refer customersdata.json for raw json data.
		Json data is imported using pandas package.
		The json data is parsed using Json package.

		The final data set have following columns
			'customerBillingAddress', 
			'customerDevice', 
			'customerEmail',
			'customerIPAddress', 
			'customerPhone', 
			'fraudulent', 
			'orderAmount',
			'orderId', 
			'orderShippingAddress', 
			'transactionId', 
			'paymentMethodId',
			'transactionAmount', 
			'transactionFailed',
			'paymentMethodRegistrationFailure', 
			'paymentMethodType',
			'paymentMethodProvider', 
			'paymentMethodIssuer', 
			'orderState',
	
	
 # Preprocessing data
 		Refer Frauddetection_model(NB) for detailed steps
 		1.Checked for null values and filled them with forward filling method.
		2.Converted the related columns to categorical data. ('customerBillingAddress', 'customerDevice', 'customerEmail', 		'customerIPAddress', 'customerPhone', 'orderId', 'orderShippingAddress', 'transactionId', 'paymentMethodId', 'paymentMethodType', 'paymentMethodProvider', 'paymentMethodIssuer')
		3. As the uniquness of data in the columns is high. Hashing encoder is select as it is good for hig dimensional data. The categorical data is converted using FeatureHasher using sklear.feature_extraction
		
# Feature importance
	Refer Frauddetection_model(NB) for detailed steps
	Found importance of features using Naive bayes model.
	Built the model using single feature at a time and selected precision as metric.
		# Feature								# precision
	'customerBillingAddress': 0.7469401709401711,
	 'customerDevice': 0.6927285861713105,
	 'customerEmail': 0.7373215339233038,
	 'customerIPAddress': 0.6198620689655172,
	 'customerPhone': 0.6646933333333334,
	 'orderAmount': 0.6604581407293272,
	 'orderId': 0.5285333333333333,
	 'orderShippingAddress': 0.697458269329237,
	 'orderState_failed': 0.6604581407293272,
	 'orderState_fulfilled': 0.6604581407293272,
	 'orderState_pending': 0.6604581407293272,
	 'paymentMethodId': 0.68,
	 'paymentMethodIssuer': 0.6604581407293272,
	 'paymentMethodProvider': 0.5682921231090244,
	 'paymentMethodRegistrationFailure': 0.6604581407293272,
	 'paymentMethodType': 0.59856,
	 'transactionAmount': 0.6604581407293272,
	 'transactionFailed': 0.6604581407293272,
	 'transactionId': 0.616
	 
 # Model and metrics
 		Refer Frauddetection_model(NB) for detailed steps
 		Selected Naive bayes algorithm for as it is computationally efficient and good in classification with high dimensional text data.
		Built the model. The following is the classification report. 
		Classification report:
              precision    recall  f1-score   support

           0       0.60      0.30      0.40        79
           1       0.35      0.65      0.46        46

    accuracy                           0.43       125
   	macro avg       0.48      0.48      0.43       125
	weighted avg       0.51      0.43      0.42       125
		
		The precision of positive class 0.35.
		
*end*
		
		
		
		

	
		
		
		
 	
  
  



