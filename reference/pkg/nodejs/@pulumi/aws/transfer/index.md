---
title: Module transfer
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/docs/tree/master/tools/tscdocgen. -->

<a href="../index.html">@pulumi/aws</a> &gt; transfer

<div class="toggleVisible" markdown="1">
<div class="collapsed" markdown="1">
<h2 class="pdoc-module-header toggleButton" title="Click to show Index">Index ▹</h2>
</div>
<div class="expanded" markdown="1">
<h2 class="pdoc-module-header toggleButton" title="Click to hide Index">Index ▾</h2>
<div class="pdoc-module-contents" markdown="1">
* <a href="#Server">class Server</a>
* <a href="#ServerArgs">interface ServerArgs</a>
* <a href="#ServerState">interface ServerState</a>

<a href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts">transfer/server.ts</a> 
</div>
</div>
</div>


<h2 class="pdoc-module-header" id="Server">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L63">class <b>Server</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">
<pre class="highlight"><span class='kd'>extends</span> <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#CustomResource'>CustomResource</a></pre>

Provides a AWS Transfer Server resource.

```hcl
resource "aws_iam_role" "foo" {
	name = "tf-test-transfer-server-iam-role"

	assume_role_policy = <<EOF
{
	"Version": "2012-10-17",
	"Statement": [
		{
		"Effect": "Allow",
		"Principal": {
			"Service": "transfer.amazonaws.com"
		},
		"Action": "sts:AssumeRole"
		}
	]
}
EOF
}

resource "aws_iam_role_policy" "foo" {
	name = "tf-test-transfer-server-iam-policy-%s"
	role = "${aws_iam_role.foo.id}"
	policy = <<POLICY
{
	"Version": "2012-10-17",
	"Statement": [
		{
		"Sid": "AllowFullAccesstoCloudWatchLogs",
		"Effect": "Allow",
		"Action": [
			"logs:*"
		],
		"Resource": "*"
		}
	]
}
POLICY
}


resource "aws_transfer_server" "foo" {
  identity_provider_type = "SERVICE_MANAGED"
  logging_role = "${aws_iam_role.foo.arn}"

  tags {
	NAME   = "tf-acc-test-transfer-server"
	ENV    = "test"
  }
}
```

<h3 class="pdoc-member-header" id="Server-constructor">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L103"> <b>constructor</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">

<pre class="highlight"><span class='kd'></span><span class='kd'>new</span> Server(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, args?: <a href='#ServerArgs'>ServerArgs</a>, opts?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>)</pre>


Create a Server resource with the given unique name, arguments, and options.

* `name` The _unique_ name of the resource.
* `args` The arguments to use to populate this resource&#39;s properties.
* `opts` A bag of options that control this resource&#39;s behavior.

</div>
<h3 class="pdoc-member-header" id="Server-get">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L72">method <b>get</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">

<pre class="highlight"><span class='kd'>public static </span>get(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, id: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#ID'>pulumi.ID</a>&gt;, state?: <a href='#ServerState'>ServerState</a>, opts?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>): <a href='#Server'>Server</a></pre>


Get an existing Server resource's state with the given name, ID, and optional extra
properties used to qualify the lookup.

</div>
<h3 class="pdoc-member-header" id="Server-getProvider">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L13">method <b>getProvider</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">

<pre class="highlight"><span class='kd'></span>getProvider(moduleMember: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>): ProviderResource | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span></pre>

</div>
<h3 class="pdoc-member-header" id="Server-isInstance">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L85">method <b>isInstance</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">

<pre class="highlight"><span class='kd'>static </span>isInstance(obj: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>): <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span></pre>


Returns true if the given object is an instance of CustomResource.  This is designed to work even when
multiple copies of the Pulumi SDK have been loaded into the same process.

</div>
<h3 class="pdoc-member-header" id="Server-identityProviderType">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L87">property <b>identityProviderType</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'>public </span>identityProviderType: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>&gt;;</pre>

The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.

</div>
<h3 class="pdoc-member-header" id="Server-invocationRole">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L91">property <b>invocationRole</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'>public </span>invocationRole: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>&gt;;</pre>

Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.

</div>
<h3 class="pdoc-member-header" id="Server-id">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L80">property <b>id</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>id: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>Output</a>&lt;<a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#ID'>ID</a>&gt;;</pre>

id is the provider-assigned unique ID for this managed resource.  It is set during
deployments and may be missing (undefined) during planning phases.

</div>
<h3 class="pdoc-member-header" id="Server-tags">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L99">property <b>tags</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'>public </span>tags: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>pulumi.Output</a>&lt;{[key: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>]: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>} | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>&gt;;</pre>

A mapping of tags to assign to the resource.

</div>
<h3 class="pdoc-member-header" id="Server-url">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L103">property <b>url</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'>public </span>url: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>&gt;;</pre>

- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.

</div>
<h3 class="pdoc-member-header" id="Server-urn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L11">property <b>urn</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>urn: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>Output</a>&lt;<a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#URN'>URN</a>&gt;;</pre>

urn is the stable logical URN used to distinctly address a resource, both before and after
deployments.

</div>
<h3 class="pdoc-member-header" id="Server-endpoint">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L83">property <b>endpoint</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'>public </span>endpoint: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

The endpoint of the Transfer Server (e.g. `s-12345678.server.transfer.REGION.amazonaws.com`)

</div>
<h3 class="pdoc-member-header" id="Server-arn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L79">property <b>arn</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'>public </span>arn: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Amazon Resource Name (ARN) of Transfer Server

</div>
<h3 class="pdoc-member-header" id="Server-loggingRole">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L95">property <b>loggingRole</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'>public </span>loggingRole: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>&gt;;</pre>

Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.

</div>
</div>
<h2 class="pdoc-module-header" id="ServerArgs">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L175">interface <b>ServerArgs</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

The set of arguments for constructing a Server resource.

<h3 class="pdoc-member-header" id="ServerArgs-identityProviderType">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L179">property <b>identityProviderType</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>identityProviderType?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.

</div>
<h3 class="pdoc-member-header" id="ServerArgs-invocationRole">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L183">property <b>invocationRole</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>invocationRole?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.

</div>
<h3 class="pdoc-member-header" id="ServerArgs-loggingRole">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L187">property <b>loggingRole</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>loggingRole?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.

</div>
<h3 class="pdoc-member-header" id="ServerArgs-tags">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L191">property <b>tags</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>tags?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;{[key: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>]: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>}&gt;;</pre>

A mapping of tags to assign to the resource.

</div>
<h3 class="pdoc-member-header" id="ServerArgs-url">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L195">property <b>url</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>url?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.

</div>
</div>
<h2 class="pdoc-module-header" id="ServerState">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L141">interface <b>ServerState</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

Input properties used for looking up and filtering Server resources.

<h3 class="pdoc-member-header" id="ServerState-arn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L145">property <b>arn</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>arn?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Amazon Resource Name (ARN) of Transfer Server

</div>
<h3 class="pdoc-member-header" id="ServerState-endpoint">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L149">property <b>endpoint</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>endpoint?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

The endpoint of the Transfer Server (e.g. `s-12345678.server.transfer.REGION.amazonaws.com`)

</div>
<h3 class="pdoc-member-header" id="ServerState-identityProviderType">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L153">property <b>identityProviderType</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>identityProviderType?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.

</div>
<h3 class="pdoc-member-header" id="ServerState-invocationRole">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L157">property <b>invocationRole</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>invocationRole?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.

</div>
<h3 class="pdoc-member-header" id="ServerState-loggingRole">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L161">property <b>loggingRole</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>loggingRole?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.

</div>
<h3 class="pdoc-member-header" id="ServerState-tags">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L165">property <b>tags</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>tags?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;{[key: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>]: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>}&gt;;</pre>

A mapping of tags to assign to the resource.

</div>
<h3 class="pdoc-member-header" id="ServerState-url">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/master/sdk/nodejs/transfer/server.ts#L169">property <b>url</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>url?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.

</div>
</div>
