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