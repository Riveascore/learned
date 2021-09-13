[Good example of TLogger](https://github.com/SonderMindOrg/sonder-rails/blob/develop/services/sondermind_billing/lib/sondermind/billing/services/transfer/transfer.rb#L62-L94)

---

## Test to assert service is called within service

```rb
describe_effects do
  it 'should execute SERVICE_TO_EXECUTE service' do
    expect(SERVICE_TO_EXECUTE).to(
      receive(:execute!).with(
        PARAMETER: PARAMETER
      )
    )

    subject.call
  end
end
```

## Successful service execution

```rb
describe_results do
  it_behaves_like 'a successfully executed service'
end
```

```rb
describe_results { it_behaves_like 'a successfully executed service' }
```

## Service Object Failure

```rb
return failure!(nil, OBJECT: 'ERROR_MESSAGE') unless OBJECT.SOMETHING?

describe_results do
  it { should be_failure }
  it { expect(subject.errors).not_to be_nil }
  it { expect(subject.errors[:OBJECT]).to include('ERROR_MESSAGE') }
end
```

## Expecting object to have new values

```rb
describe_state_after do
  it 'creates a ClaimCancellation containing the reincarnated_claim_id' do
    expect(claim.claim_cancellation.reincarnated_claim_id).to eq(reincarnated_claim.id)
  end
end
```

## Should or shouldn't change attributes

```rb
it { should_not change(canceled_invoice.reload.attributes) }
it { should_not change(successful_invoice.reload.attributes) }
```